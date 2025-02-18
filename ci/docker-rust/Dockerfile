# Note: when the rust version is changed also modify
# ci/rust-version.sh to pick up the new image tag
FROM rust:1.69.0

RUN set -x \
 && apt update \
 && apt-get install apt-transport-https \
 && echo deb https://apt.buildkite.com/buildkite-agent stable main > /etc/apt/sources.list.d/buildkite-agent.list \
 && apt-key adv --no-tty --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys 32A37959C2FA5C3C99EFBC32A79206696452D198 \
 && curl -fsSL https://deb.nodesource.com/setup_current.x | bash - \
 && apt update \
 && apt install -y \
      buildkite-agent \
      clang \
      cmake \
      jq \
      lcov \
      libudev-dev \
      mscgen \
      nodejs \
      net-tools \
      rsync \
      sudo \
      golang \
      unzip \
      lld \
      \
 && apt remove -y libcurl4-openssl-dev \
 && rm -rf /var/lib/apt/lists/* \
 && node --version \
 && npm --version \
 && rustup component add rustfmt \
 && rustup component add clippy \
 && rustup target add wasm32-unknown-unknown \
 && cargo install cargo-audit \
 && cargo install cargo-hack \
 && cargo install cargo-sort \
 && cargo install mdbook \
 && cargo install mdbook-linkcheck \
 && cargo install svgbob_cli \
 && cargo install wasm-pack \
 && cargo install sccache \
 && rustc --version \
 && cargo --version
