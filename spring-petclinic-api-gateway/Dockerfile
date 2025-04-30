FROM --platform=linux/amd64 public.ecr.aws/docker/library/python:3.10

# Set environment variables from build arguments
ENV RUM_APPLICATION_ID=$NEXT_PUBLIC_RUM_APPLICATION_ID
ENV RUM_IDENTITY_POOL_ID=$NEXT_PUBLIC_RUM_IDENTITY_POOL_ID
ENV AWS_REGION=$NEXT_PUBLIC_AWS_REGION
ENV BACKEND_API_URL=$BACKEND_API_URL

WORKDIR /app
RUN mkdir -p /app/tmp && \
    export TMPDIR=/app/tmp && \
    pip install --no-cache-dir django djangorestframework boto3 py_eureka_client psycopg2 requests

COPY . /app
EXPOSE 8800
