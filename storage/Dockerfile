FROM minio/minio

# Copy local files to the container
COPY ./*_data /data

# Set environment variables from .env file
ENV MINIO_ACCESS_KEY=$MINIO_ACCESS_KEY
ENV MINIO_SECRET_KEY=$MINIO_SECRET_KEY

# Command to import local data to MinIO
CMD ["sh", "-c", "mc config host add minio http://localhost:9000 $MINIO_ACCESS_KEY $MINIO_SECRET_KEY && mc cp /data minio/spark-bucket/ --recursive"]
