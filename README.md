<p align="center">
  <img src="https://raw.githubusercontent.com/realworldprivacy/energetic-ai/main/logo.png" alt="EnergeticAI" width="369" height="84">
</p>

<p align="center">Run open-source AI in serverless functions, up to 67x faster. Compatible with Tensorflow.js.</p>

# EnergeticAI

EnergeticAI is a distribution of TensorFlow.js optimized for serverless functions:

- **small module size** (~3 MB vs. 146 MB - 513 MB for stock TensorFlow.js)
- **fast cold-start inference** (~50 ms vs. 2000+ ms for stock TensorFlow.js)
- **incredible ease-of-use** (pre-trained models for common cases)

It's intended to be a condensed replacement for TensorFlow.js, so you can use it with much existing code and models.

## Install

EnergeticAI is available on NPM.

Install the **core package**, along with any **model libraries** you want to use (e.g. embeddings):

```bash
npm install @energetic-ai/core @energetic-ai/embeddings @energetic-ai/model-embeddings-en
```

You can see a full list of packages below.

## Usage

Here's an example of using the embeddings model:

```js
import { initModel, distance } from "@energetic-ai/embeddings";
import { modelSource } from "@energetic-ai/model-embeddings-en";
(async () => {
  const model = await initModel(modelSource);
  const embeddings = await model.embed(["hello", "world"]);
  console.log(distance(embeddings[0], embeddings[1])));
})();
```

## Packages

This repository contains the following packages:

| Package                               | Description                                                          |
| ------------------------------------- | -------------------------------------------------------------------- |
| **@energetic-ai/core**                | The core EnergeticAI library, comparable to `@tensorflow\tfjs-core`. |
| **@energetic-ai/classifiers**         | Classifiers model library.                                           |
| **@energetic-ai/embeddings**          | Embeddings model library.                                            |
| **@energetic-ai/model-embeddings-en** | English embeddings model weights.                                    |

See the readmes in the [packages](packages) directory for more information.

## Examples

See the [examples](examples) directory for examples.

## Development

This repository uses [Lerna](https://lerna.js.org/) to manage packages, and [Vitest](https://vitest.dev/) to run tests.

## License

[Apache 2.0](LICENSE), except for dependencies.

## Acknowledgements

This project is derived from [TensorFlow.js](https://github.com/tensorflow/tfjs), the [Universal Sentence Encoder model library](https://github.com/tensorflow/tfjs-models) and [Universal Sentence Encoder Lite model weights](https://tfhub.dev/tensorflow/tfjs-model/universal-sentence-encoder-lite/1/default/1), which are also Apache 2.0 licensed.

```

```
