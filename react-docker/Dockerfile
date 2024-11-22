FROM node:18-alpine3.19

# Create a group and user
RUN addgroup reactGroup && adduser -S -G reactGroup reactUser

# Set the working directory
WORKDIR /app

# Create data dir
RUN mkdir data

# Copy application package file
COPY package.json .

# Change ownership of the files to the new user
RUN chown -R reactUser:reactGroup /app

# Switch to the new user
USER reactUser

# Install dependencies
RUN npm install

# Copy application files
COPY . .

# Set environment variable
ENV API_URL=https://example.com/api

# Run build command
RUN npm run build

# Expose the application port
EXPOSE 8080

# Run npm command
CMD ["npm","run","preview"] 

# بیلد گرفتن از فایل داکر
# docker build -t . raect-docker:v .
# اجرای ایمیج بر روی پورت 80 به وسیله والیوم و ساخت دایرکتوری دیتا
# docker run -d -p 80:8080 -v app-data:/app/data react-docker:v
# اجرا به صورتی که با تغییر کد تغییرات بر روی کانتینر هم اعمال شود
# docker run -d -p 80:8080 -v E:\react-docker:/app react-docker:v