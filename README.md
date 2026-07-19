# aws-vpc-subnet-calculator

[![GitHub Pages](https://img.shields.io/badge/GitHub%20Pages-Live-brightgreen)](https://ishiharatma.github.io/aws-vpc-subnet-calculator/)

![screenshot](/images/screenshot-en.png)
![screenshot-result](/images/screenshot-result-en.png)

A browser-based tool to calculate and visualize Amazon VPC subnet CIDRs across multiple tiers and AZs, with free address space detection.

*他の言語で読む:* [![🇯🇵 日本語](https://img.shields.io/badge/%F0%9F%87%AF%F0%9F%87%B5-日本語-white)](./README.ja.md) [![🇺🇸 English](https://img.shields.io/badge/%F0%9F%87%BA%F0%9F%87%B8-English-white)](./README.md)

## Features

- **Variable VPC CIDR** — Enter any valid CIDR block (e.g. `10.0.0.0/22`)
- **Multi-tier subnet design** — Add, remove, and configure tiers with custom subnet masks
- **Drag-and-drop reordering** — Reorder tiers by dragging them into place
- **Dual AZ support** — Automatically allocates subnets across `ap-northeast-1a` and `ap-northeast-1c`
- **TGW tail allocation** — Optionally reserves TGW subnets from the end of the VPC address space
- **Free address space detection** — Detects and displays all gaps including alignment gaps, space between forward-allocated and TGW subnets, and trailing space
- **AWS reserved address aware** — Displays usable host count after subtracting the 5 AWS-reserved addresses per subnet
- **Japanese/English language switching** — Toggle the UI language with a button; auto-detects the browser's language on load
- **Dark mode support** — Automatically adapts to system color scheme

## Default Configuration

| Tier | Mask |
|------|------|
| Private-App | /24 |
| Public | /26 |
| Private-DB | /26 |
| VPC Endpoint | /26 |
| TGW | /28 (tail allocation) |

VPC CIDR default: `10.0.0.0/22`

## Usage

Open `index.html` in any modern browser — no build step or dependencies required.

Hosted on GitHub Pages: `https://ishiharatma.github.io/aws-vpc-subnet-calculator/`

## Deployment

```bash
git clone https://github.com/ishiharatma/aws-vpc-subnet-calculator.git
cd aws-vpc-subnet-calculator
# Place index.html under the docs/ directory
# Push to main branch
# Enable GitHub Pages: Settings > Pages > Branch: main / docs
```

## Repository Structure

```
aws-vpc-subnet-calculator/
├── README.md
├── README.ja.md
├── images/
│   ├── screenshot-en.png
│   └── screenshot-ja.png
└── docs/
    └── index.html
```

## License

MIT License — Copyright (c) 2026 Issy

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
