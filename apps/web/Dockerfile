FROM node:18-alpine
ENV NODE_ENV=production
USER nextjs
WORKDIR /api
COPY --chown=nextjs .env.example .env.local
COPY --chown=nextjs package*.json ./
RUN npm install
COPY --chown=nextjs . .
RUN npm run build   
ENV HOST=0.0.0.0 PORT=8080
EXPOSE ${PORT}
CMD [ "node", "." ]