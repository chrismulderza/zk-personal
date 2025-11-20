---
id: "923ed2"
title: "MinIO Recipes"
type: "note"
tags: [s3, storage, minio, k8s]
date: "2025-11-20"
---

# MinIO Recipes

## Automating MinIO File Cleanup

Cleanup Script. I needed to create a bash script to handle the cleanup process
using `mc`. The following script ended up working just fine:

```bash
#!/bin/bash

# Set variables
MINIO_ENDPOINT="http://localhost:9000"
BUCKET_NAME="my-bucket"
RETENTION_DAYS=7
ACCESS_KEY="my-access-key"
SECRET_KEY="my-secret-key"

# Configure mc client
mc alias remove myminio 2>/dev/null || true
mc alias set myminio $MINIO_ENDPOINT $ACCESS_KEY $SECRET_KEY

# Verify connection and bucket existence
echo "Verifying connection to MinIO server..."
if ! mc ls myminio/$BUCKET_NAME > /dev/null 2>&1; then
  echo "Error: Cannot access bucket. Please check your credentials and bucket name."
  exit 1
fi

# Log start time
echo "Starting MinIO cleanup at $(date)"

# Find and delete files older than retention period
echo "Finding files older than $RETENTION_DAYS days in bucket $BUCKET_NAME..."

# Use mc find to locate and delete old files
mc find myminio/$BUCKET_NAME --older-than "${RETENTION_DAYS}d" --exec "mc rm --force {}"

echo "Cleanup completed at $(date)"
```
