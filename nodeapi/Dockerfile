FROM node:14 AS nodeapi-build
ENV NODEAPI_BUILD /nodeapi_build
WORKDIR $NODEAPI_BUILD
COPY ./ $NODEAPI_BUILD
RUN cd $NODEAPI_BUILD && npm install

FROM node:14
ENV NODEAPI_RUN /nodeapi
WORKDIR $NODEAPI_RUN
COPY --from=nodeapi-build /nodeapi_build/ ./
RUN ls
EXPOSE 5000
CMD ["npm", "run", "start"]
# Test3
