build:
	cd ffi && cargo build --release --no-default-features --features "rust-secp256k1 std rlp"
	cp ffi/target/release/libsputnikvm_ffi.a libsputnikvm.a
	cp ffi/target/release/libsputnikvm_ffi.so libsputnikvm.so | true

build-musl:
	cd ffi && docker run --rm -it -v "$(shell pwd)/ffi":/home/rust/src ekidd/rust-musl-builder cargo build --release
	cp ffi/target/x86_64-unknown-linux-musl/release/libsputnikvm_ffi.a libsputnikvm.a

debug:
	cd ffi && cargo build
	cp ffi/target/debug/libsputnikvm_ffi.a libsputnikvm.a
	cp ffi/target/debug/libsputnikvm_ffi.so libsputnikvm.so | true
