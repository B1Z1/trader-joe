# This file is generated by Nx.
#
# Build the docker image with `npx nx docker-build trader-joe-backend`.
# Tip: Modify "docker-build" options in project.json to change docker build args.
#
# Run the container with `docker run -p 3000:3000 -t trader-joe-backend`.
FROM docker.io/node:lts-alpine

ENV HOST=0.0.0.0
ENV PORT=3000

WORKDIR /app

RUN addgroup --system trader-joe-backend && \
          adduser --system -G trader-joe-backend trader-joe-backend

COPY dist/apps/trader-joe-backend trader-joe-backend
RUN chown -R trader-joe-backend:trader-joe-backend .

# You can remove this install step if you build with `--bundle` option.
# The bundled output will include external dependencies.
RUN npm --prefix trader-joe-backend --omit=dev -f install

CMD [ "node", "trader-joe-backend" ]
