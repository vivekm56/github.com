# Use the official Go image as the base image
FROM golang:1.16-alpine3.13
# RUN mkdir /app
ADD . /app
# Set the working directory inside the container
WORKDIR /notes-app

# Copy the Go module files to the working directory
COPY go.mod go.sum ./
# Download and cache the Go modules
RUN go mod download

# Copy the project files to the working directory
COPY . .
# RUN chmod +x /notes-app

# Build the Go application
RUN go build -o /noteTakingApplication
# Create a non-root user
# RUN groupadd -g 10001 appuser && \
#     useradd -r -u 10001 -g appuser appuser
# EXPOSE 8080
# Set the ownership of the files to the non-root user
# RUN chown -R appuser:appuser /noteTakingApplication

# Set the user as the non-root user
# USER appuser
# Set the entry point command to run the Go application
CMD ["/noteTakingApplication"]






# Stage 1: Build the Go application
# FROM golang:1.16 AS builder

# WORKDIR /app

# Copy the Go module dependency files
# COPY go.mod go.sum ./

# Download and install the Go module dependencies
# RUN go mod download

# Copy the project files into the container
# COPY . .

# Build the Go application
# RUN CGO_ENABLED=0 GOOS=linux go build -o main/
# RUN CGO_ENABLED=0 GOOS=linux go build -o /notetakingapplication

# Stage 2: Create the final Docker image
# FROM alpine:latest

# Set the working directory inside the container
# WORKDIR /app

# Copy the built Go application from the builder stage
# COPY --from=builder /app/main .

# Expose the port that the application listens on
# EXPOSE 8080

# Run the Go application
# CMD ["notetakingapplication"]
