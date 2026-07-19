# aws-vpc-subnet-calculator

[![GitHub Pages](https://img.shields.io/badge/GitHub%20Pages-Live-brightgreen)](https://ishiharatma.github.io/aws-vpc-subnet-calculator/)

![screenshot](/images/screenshot-ja.png)

複数ティア・AZをまたいだAWS VPCサブネットCIDRの計算と空きアドレス空間の可視化を行うブラウザツール。

*Read this in other languages:* [![🇯🇵 日本語](https://img.shields.io/badge/%F0%9F%87%AF%F0%9F%87%B5-日本語-white)](./README.ja.md) [![🇺🇸 English](https://img.shields.io/badge/%F0%9F%87%BA%F0%9F%87%B8-English-white)](./README.md)

## 機能

- **VPC CIDR 可変入力** — 任意のCIDRブロックを入力可能（例：`10.0.0.0/22`）
- **マルチティア設計** — ティアの追加・削除・サブネットマスク指定が自由に行える
- **ドラッグ&ドロップで並び替え** — ティアの順序をドラッグ操作で自由に入れ替え可能
- **2AZ対応** — `ap-northeast-1a` / `ap-northeast-1c` へ自動で振り分けて割り当て
- **TGW末尾割り当て** — ティア名に「TGW」を含む場合、VPCアドレス空間の末尾から逆算して割り当て（ON/OFF切り替え可能）
- **空きアドレス空間の検出** — アライメントギャップ・前詰めとTGWの間・VPC末尾の余剰など、すべての空き範囲を検出・表示
- **AWSの予約アドレス考慮** — サブネットごとに5アドレスを控除した有効ホスト数を表示
- **ダークモード対応** — システムのカラースキームに自動追従

## デフォルト設定

| ティア | マスク |
|--------|--------|
| Private-App | /24 |
| Public | /26 |
| Private-DB | /26 |
| VPCエンドポイント | /26 |
| TGW | /28（末尾割り当て）|

VPC CIDRデフォルト値：`10.0.0.0/22`

## 使い方

`index.html` をブラウザで開くだけで動作します。ビルド不要・外部依存なし。

GitHub Pages URL：`https://ishiharatma.github.io/aws-vpc-subnet-calculator/`

## デプロイ手順

```bash
git clone https://github.com/ishiharatma/aws-vpc-subnet-calculator.git
cd aws-vpc-subnet-calculator
# index.html を docs/ ディレクトリに配置
# main ブランチにプッシュ
# GitHub Pages を有効化: Settings > Pages > Branch: main / docs
```

## リポジトリ構成

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

## ライセンス

MIT License — Copyright (c) 2026 Issy

本ソフトウェアは、MITライセンスのもとで提供されます。著作権表示およびライセンス文を、ソフトウェアのすべての複製または重要な部分に記載することを条件に、無償で使用・複製・改変・配布・再ライセンス・販売することが許可されます。

本ソフトウェアは「現状のまま」提供され、商品性・特定目的への適合性・非侵害性に関する保証を含む、いかなる明示・黙示の保証も行いません。
