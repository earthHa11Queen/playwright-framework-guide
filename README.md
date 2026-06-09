# playwright-framework-guide

A design philosophy and architecture guide for building E2E test automation systems on top of Playwright.

Born from **1,500+ test case implementations** in real SIer projects.

---

## About This Repository

Playwright's official documentation explains how to use the API.
What it doesn't cover is **how to design and operate a project at 1,500+ test cases.**

This guide is a record of design philosophy and decisions,
systematized from hands-on implementation experience in SIer projects —
covering the architecture of the **entire test automation system** built on top of Playwright.

Every guideline comes with its rationale:
from directory structure and naming conventions,
to data management and AI integration.

---

## Documents

### 1. [Framework Design Philosophy](docs/01_framework-design.md)

Design principles for a Playwright-based E2E test automation system.

- Complete separation architecture between test scripts and Page Objects
- Two-layer structure: Static Root (stable anchors) and Scope Switching (dynamic cursors)
- Naming conventions: unified policy for `input~` / `check~` / `submit~` / `click~`
- Test data management (CSV vs TypeScript objects — criteria for choosing)
- Which work areas benefit most from Playwright + AI integration (completion, review, data generation, etc.)
- Rules on loop usage and the requirement for at least two nested `describe` levels

### 2. [Test Strategy](docs/02_test-strategy.md)

A document organizing the boundaries of test phases and the overall picture of deliverables.

- Seven test phase definitions: unit screen, unit API, integration screen, integration API, system, performance/load, and penetration
- One-to-one correspondence model between test scripts and test specifications
- Four-tier method classification: generic methods, common methods, screen-specific methods, and test data methods
- Components of a test specification (case number, perspective, operation steps, expected results, re-execution management)
- The principle of "never mixing perspectives" in specification design

---

## About `schemas/`

The `schemas/` directory contains structure definition files used in unit module test design.
Further documentation on this content is planned.

---

## Related Repository

- [mirror-framework](https://github.com/earthHa11Queen/mirror-framework)
  A design framework for finite test scenario generation using domain definition and boolean operations.
  It forms the theoretical foundation for the test strategy and scenario generation approach in this guide.

---

## License

[CC BY-SA 4.0](LICENSE)

This repository handles design philosophy and documentation rather than code,
so the Creative Commons Attribution-ShareAlike license applies.
When citing, adapting, or redistributing, please credit the original author
and apply the same license.

---

---

# playwright-framework-guide（日本語）

PlaywrightによるE2Eテスト自動化システムを構築するための設計思想・アーキテクチャガイドです。

1500ケース以上の実装経験から生まれた、Playwright E2Eテスト自動化システムの設計ガイドラインです。

---

## このリポジトリについて

Playwrightの公式ドキュメントはAPIの使い方を教えてくれますが、
**1500ケース規模のプロジェクトをどう設計・運用するか**については書かれていません。

本ガイドは、SIer案件での実際の実装経験をもとに体系化した、
Playwright **上に構築するテスト自動化システム全体**の設計思想と判断の記録です。

「なぜそうするのか」という根拠とともに、ファイル構成・命名規則・データ管理・AI統合まで扱います。

---

## ドキュメント

### 1. [フレームワーク設計思想](docs/01_framework-design.md)

Playwrightを用いたE2Eテスト自動化システムの設計原則を解説します。

- テストスクリプトとPage Object の完全分離アーキテクチャ
- Static Root（静的基盤）と Scope Switching（動的スコープ切り替え）の2層構造
- 命名規則：`input~` / `check~` / `submit~` / `click~` の統一方針
- テストデータの管理方針（CSV vs TypeScriptオブジェクト、使い分けの判断基準）
- AIとPlaywrightの融和性が高い作業領域の整理（補完・レビュー・データ生成など）
- ループ処理の使用可否ルールと `describe` 2階層以上の必須化

### 2. [テスト戦略](docs/02_test-strategy.md)

テスト工程の区切りと成果物の全体像を整理したドキュメントです。

- 単体画面・単体API・結合画面・結合API・総合・性能負荷・ペネトレーションの7工程定義
- テストスクリプトとテスト仕様書の1対1対応モデル
- 汎用メソッド・共通メソッド・固有メソッド・テストデータメソッドの4種分類
- テスト仕様書の構成要素（ケースナンバー・観点・操作手順・想定結果・再実施管理）
- 「観点を混ぜ込まない」仕様書設計の原則

---

## schemas について

`schemas/` ディレクトリには、単体のモジュールテスト設計で使用する構造定義ファイルを格納しています。
今後、この内容についても詳しく記載する予定です。

---

## 関連リポジトリ

- [mirror-framework](https://github.com/earthHa11Queen/mirror-framework)
  - テストシナリオをドメインとboolean演算で有限算出する設計フレームワーク。
    本ガイドのテスト戦略・テストシナリオ生成の理論的基盤です。

---

## ライセンス

[CC BY-SA 4.0](LICENSE)

本リポジトリはコードではなく設計思想・ドキュメントを扱うため、
Creative Commons（表示 - 継承）ライセンスを採用しています。
引用・改変・再配布の際は原著者の表示と同一ライセンスの適用をお願いします。
