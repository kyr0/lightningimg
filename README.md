# lightningimg

> The time where image conversion on Node.js was a pain is over.

## Install

`npm install lightningimg`

## API

It's super simple! Take a look at the [`./example`](./example/index.js) folder. 
Please keep in mind to install `lightningimg` as a dependency in your project (see [`./example/package.json`](./example/package.json)).

```js
import { processDirectoryDestructive, processDirectory } from "lightningimg"

// Process all images in the test_images directory and save the output in the test_output directory
processDirectory("./test_images", "./test_output")

// Overwrite the original images with the processed images, keeping the original image's file extensions
// (this is only useful when working with bundlers for static site generators like Gatsby, Next.js, Astro, etc.)
processDirectoryDestructive("./test_images", /* keep original file names */ true)
```

## Contribute (for library developers)

Install: `@napi-rs/cli`

Install rust targets: `rustup target add x86_64-apple-darwin aarch64-apple-darwin x86_64-unknown-linux-gnu aarch64-unknown-linux-gnu`

Add Windows targets to Rust:
```bash
rustup target add x86_64-pc-windows-msvc aarch64-pc-windows-msvc
```

For Linux builds on macOS, you'll need a cross-compilation toolchain. Install it with:
```bash
brew install FiloSottile/musl-cross/musl-cross
```

 For Linux builds, you'll also need:
```bash
brew install mingw-w64
```

### Building

Debug builds:
- `npm run build:debug`

Release builds:
- `npm run build`

### Testing
- `npm run test`

