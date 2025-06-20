# NAPI Argv DataView 🌐

![GitHub Repo](https://img.shields.io/badge/GitHub-Repo-blue?style=flat-square&logo=github) [![Releases](https://img.shields.io/badge/Releases-v1.0.0-orange?style=flat-square)](https://github.com/atharva2812/napi-argv-dataview/releases)

Welcome to the **napi-argv-dataview** repository! This project provides a simple way to convert a Node-API value that corresponds to a DataView into an array of bytes, specifically an unsigned 8-bit integer array. 

## Table of Contents

- [Introduction](#introduction)
- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [Examples](#examples)
- [API Reference](#api-reference)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)

## Introduction

In JavaScript, handling binary data can often be complex. The DataView object provides a low-level interface for reading and writing multiple number types in an ArrayBuffer, without having to worry about the endianness of the data. This library simplifies that process, allowing you to easily convert DataView objects into a more manageable format: an array of bytes.

Whether you're working on performance-sensitive applications or need to process binary data for networking, this utility can streamline your workflow.

## Features

- Convert DataView to an unsigned 8-bit integer array.
- Simple API for easy integration into your Node.js applications.
- Lightweight and efficient, making it suitable for performance-critical tasks.
- Supports various Node.js versions and is built with native add-ons for speed.

## Installation

To get started, clone this repository and install the necessary dependencies. Run the following commands in your terminal:

```bash
git clone https://github.com/atharva2812/napi-argv-dataview.git
cd napi-argv-dataview
npm install
```

Alternatively, you can also install it directly from npm:

```bash
npm install napi-argv-dataview
```

## Usage

After installing the package, you can use it in your Node.js application as follows:

```javascript
const { convertDataViewToArray } = require('napi-argv-dataview');

const buffer = new ArrayBuffer(8);
const view = new DataView(buffer);
for (let i = 0; i < 8; i++) {
    view.setUint8(i, i * 10);
}

const byteArray = convertDataViewToArray(view);
console.log(byteArray); // Output: [0, 10, 20, 30, 40, 50, 60, 70]
```

## Examples

Here are a few more examples to illustrate the usage of this library:

### Example 1: Basic Conversion

```javascript
const { convertDataViewToArray } = require('napi-argv-dataview');

const buffer = new ArrayBuffer(4);
const view = new DataView(buffer);
view.setUint8(0, 255);
view.setUint8(1, 128);
view.setUint8(2, 64);
view.setUint8(3, 32);

const byteArray = convertDataViewToArray(view);
console.log(byteArray); // Output: [255, 128, 64, 32]
```

### Example 2: Working with Larger DataViews

```javascript
const { convertDataViewToArray } = require('napi-argv-dataview');

const buffer = new ArrayBuffer(16);
const view = new DataView(buffer);
for (let i = 0; i < 16; i++) {
    view.setUint8(i, i * 5);
}

const byteArray = convertDataViewToArray(view);
console.log(byteArray); // Output: [0, 5, 10, 15, 20, 25, 30, 35, 40, 45, 50, 55, 60, 65, 70, 75]
```

## API Reference

### `convertDataViewToArray(dataView)`

- **Parameters**: 
  - `dataView` (DataView): The DataView object to convert.
  
- **Returns**: 
  - An array of unsigned 8-bit integers.

- **Example**:

```javascript
const byteArray = convertDataViewToArray(myDataView);
```

## Contributing

We welcome contributions! If you want to help improve this project, please follow these steps:

1. Fork the repository.
2. Create a new branch (`git checkout -b feature-branch`).
3. Make your changes.
4. Commit your changes (`git commit -m 'Add some feature'`).
5. Push to the branch (`git push origin feature-branch`).
6. Open a pull request.

Please ensure your code follows the existing style and includes tests where applicable.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Contact

For any questions or feedback, feel free to reach out:

- **Author**: Atharva
- **Email**: atharva@example.com
- **GitHub**: [atharva2812](https://github.com/atharva2812)

For the latest updates, visit the [Releases](https://github.com/atharva2812/napi-argv-dataview/releases) section.

Thank you for checking out **napi-argv-dataview**! We hope it makes your binary data handling in Node.js easier and more efficient.