FROM debian:bookworm-slim
RUN apt-get update && apt-get install -y --no-install-recommends curl ca-certificates zlib1g libstdc++6 \
 && rm -rf /var/lib/apt/lists/*
ARG SOUR_VERSION=0.2.5
WORKDIR /sour
# Official prebuilt release: server binary (web client embedded) + game assets (~380 MB)
RUN curl -fsSL "https://github.com/cfoust/sour/releases/download/v${SOUR_VERSION}/sour_${SOUR_VERSION}_linux_amd64.tar.gz" | tar xz
EXPOSE 1337/tcp 28785/udp
CMD ["./sour"]
