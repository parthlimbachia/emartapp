FROM node:14 AS web-build
ENV FRONTEND /emartapp
WORKDIR $FRONTEND
COPY ./ $FRONTEND
RUN cd $FRONTEND && npm install && npm run build --prod

# Use official nginx image as the base image
FROM nginx:latest

# Copy the build output to replace the default nginx contents.
COPY --from=web-build /emartapp/dist/client/ /usr/share/nginx/html
COPY nginx.conf /etc/nginx/conf.d/default.conf

# Expose port 4200
EXPOSE 4200
