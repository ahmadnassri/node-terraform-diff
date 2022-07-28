# Terraform Plan Unidiff

Generate a human readable diff of Terraform Plan changes, using [Unified format (`unidiff`)][]

[![license][license-img]][license-url]
[![release][release-img]][release-url]
[![semantic][semantic-img]][semantic-url]

## Usage

### CLI

``` bash
npx @ahmadnassri/terraform-unidiff /path/to/plan.json
```

### Library

#### Installation

``` bash
npm install @ahmadnassri/terraform-unidiff
```

#### API

``` js
const unidiff = require('@ahmadnassri/terraform-unidiff')

const plan = fs.readFileSync('path/to/plan.json')

const { summary, patches } = unidiff(plan)

console.log(patches) // array of changes in unidiff format
console.log(summary) // object with changes counts { create: 1, update: 3, delete: 0 }
```

## Plan JSON

to obtain a Terraform plan in JSON format, run the following command:

``` bash
terraform plan -out terraform.plan && terraform show -json terraform.plan > terraform.json
```

  [Unified format (`unidiff`)]: https://en.wikipedia.org/wiki/Diff#Unified_format

----
> Author: [Ahmad Nassri](https://www.ahmadnassri.com/) &bull;
> Twitter: [@AhmadNassri](https://twitter.com/AhmadNassri)

[license-url]: LICENSE
[license-img]: https://badgen.net/github/license/ahmadnassri/node-terraform-unidiff

[release-url]: https://github.com/ahmadnassri/node-terraform-unidiff/releases
[release-img]: https://badgen.net/github/release/ahmadnassri/node-terraform-unidiff

[semantic-url]: https://github.com/ahmadnassri/node-terraform-unidiff/actions?query=workflow%3Arelease
[semantic-img]: https://badgen.net/badge/📦/semantically%20released/blue
