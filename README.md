# hello-wasi-http

https://opensource.microsoft.com/blog/2024/09/25/distributing-webassembly-components-using-oci-registries/

```sh
cargo component build --release
mv target/wasm32-wasip1/release/hello_wasi_http.wasm ./hello_wasi_http.wasm
```

```sh
wasmtime serve hello_wasi_http.wasm
```

```sh
curl 127.0.0.1:8080
```

```sh
wkg oci push ghcr.io/z63d/hello-wasi-http:latest hello_wasi_http.wasm
```

```sh
regctl manifest get ghcr.io/z63d/hello-wasi-http:latest
```

```sh
wkg oci pull ghcr.io/z63d/hello-wasi-http:latest -o app.wasm
```

```sh
wasmtime serve app.wasm --addr 127.0.0.1:3000
```
