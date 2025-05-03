# Stage 1
FROM python:3.10-slim as builder
WORKDIR /app
COPY requirements.txt .
RUN pip install --upgrade pip && pip install -r requirements.txt
COPY . .

# Stage 2
FROM gcr.io/distroless/python3
COPY --from=builder /app /app
WORKDIR /app
CMD ["main.py"]
