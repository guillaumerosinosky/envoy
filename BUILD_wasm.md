# change .bazelrc
# build:linux --define wasm=wavm # or wasmtime or wamr
ENVOY_DOCKER_BUILD_DIR=./build ./ci/run_envoy_docker.sh './ci/do_ci.sh release.server_only'

# https://www.envoyproxy.io/docs/envoy/latest/start/building/local_docker_build
docker tag envoyproxy/envoy:v1.29.2 grosinosky/envoy:v1.29_wavm
docker push grosinosky/envoy:v1.29_wavm