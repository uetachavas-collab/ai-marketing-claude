<p align="center">
  <img src="banner.svg" alt="AI Marketing Suite for Claude Code" width="100%">
</p>

# AI Marketing Suite for Claude Code

[Claude Code](https://docs.anthropic.com/en/docs/claude-code) 向けの包括的なマーケティング分析・自動化スキルシステムです。ウェブサイトの監査、広告コピーの生成、メールシーケンスの構築、コンテンツカレンダーの作成、競合分析、クライアント向けPDFレポートの出力まで、すべてターミナル上で完結します。

**AIを活用したマーケティングサービスを展開したい起業家・代理店オーナー・個人事業主向けのツールです。**

---

## 何ができるか

Claude Codeでコマンドを入力するだけで、即座に実用的なマーケティング分析が得られます:

```
> /market audit https://calendly.com

5つの並列エージェントを起動中...
✓ コンテンツ & メッセージング分析     — スコア: 72/100
✓ コンバージョン最適化               — スコア: 58/100
✓ SEO & 検索露出                     — スコア: 81/100
✓ 競合ポジショニング                  — スコア: 64/100
✓ ブランド & 信頼性                   — スコア: 76/100
✓ 成長 & 戦略                         — スコア: 61/100

総合マーケティングスコア: 69/100

フルレポートを MARKETING-AUDIT.md に保存しました
```

---

## インストール

### ワンコマンドインストール

```bash
curl -fsSL https://raw.githubusercontent.com/zubair-trabzada/ai-marketing-claude/main/install.sh | bash
```

### 手動インストール

```bash
git clone https://github.com/zubair-trabzada/ai-marketing-claude.git
cd ai-marketing-claude
./install.sh
```

### オプション: PDFレポート対応

```bash
pip install reportlab
```

---

## コマンド一覧

| コマンド | 機能 |
|---------|-------------|
| `/market audit <url>` | 5つの並列エージェントによる完全なマーケティング監査 |
| `/market quick <url>` | 60秒のマーケティングスナップショット |
| `/market copy <url>` | 改善前後の例を含む最適化コピーの生成 |
| `/market emails <topic>` | 完全なメールシーケンスの生成 |
| `/market social <topic>` | 30日間のSNSコンテンツカレンダー |
| `/market ads <url>` | 全プラットフォーム向け広告クリエイティブとコピー |
| `/market funnel <url>` | セールスファネルの分析と最適化 |
| `/market competitors <url>` | 競合インテリジェンスレポート |
| `/market landing <url>` | ランディングページのCRO分析 |
| `/market launch <product>` | 製品ローンチプレイブック |
| `/market proposal <client>` | クライアント提案書の生成 |
| `/market report <url>` | 完全なマーケティングレポート（Markdown） |
| `/market report-pdf <url>` | プロフェッショナルなマーケティングレポート（PDF） |
| `/market seo <url>` | SEOコンテンツ監査 |
| `/market brand <url>` | ブランドボイスの分析とガイドライン |

---

## アーキテクチャ

```
ai-marketing-claude/
├── market/SKILL.md                     # メイン司令塔（全 /market コマンドの振り分け）
│
├── skills/                             # 14個のサブスキル
│   ├── market-audit/SKILL.md           # 総合監査（5エージェントを起動・統括）
│   ├── market-copy/SKILL.md            # コピーライティング分析と改善案生成
│   ├── market-emails/SKILL.md          # メールシーケンス生成
│   ├── market-social/SKILL.md          # SNSコンテンツカレンダー生成
│   ├── market-ads/SKILL.md             # 広告クリエイティブとコピー生成
│   ├── market-funnel/SKILL.md          # セールスファネル分析と改善
│   ├── market-competitors/SKILL.md     # 競合調査・比較レポート
│   ├── market-landing/SKILL.md         # ランディングページのコンバージョン改善
│   ├── market-launch/SKILL.md          # 製品ローンチ計画の作成
│   ├── market-proposal/SKILL.md        # クライアント提案書の作成
│   ├── market-report/SKILL.md          # マーケティングレポート（Markdown）
│   ├── market-report-pdf/SKILL.md      # マーケティングレポート（PDF）
│   ├── market-seo/SKILL.md             # SEOコンテンツ監査
│   └── market-brand/SKILL.md           # ブランドボイス分析・ガイドライン作成
│
├── agents/                             # 5つの並列サブエージェント
│   ├── market-content.md               # コンテンツ・メッセージング分析
│   ├── market-conversion.md            # コンバージョン率改善分析
│   ├── market-competitive.md           # 競合ポジショニング分析
│   ├── market-technical.md             # テクニカルSEO・計測タグ確認
│   └── market-strategy.md              # ブランド・価格・成長戦略分析
│
├── scripts/                            # Pythonユーティリティスクリプト
│   ├── analyze_page.py                 # ウェブページマーケティング分析
│   ├── competitor_scanner.py           # 競合ウェブサイトスキャナー
│   ├── social_calendar.py              # SNSコンテンツカレンダー生成ツール
│   └── generate_pdf_report.py          # PDFレポート生成ツール
│
├── templates/                          # マーケティングテンプレート
│   ├── email-welcome.md                # ウェルカムメールシーケンス（5通）
│   ├── email-nurture.md                # リードナーチャリングシーケンス（6通）
│   ├── email-launch.md                 # 製品ローンチシーケンス（8通）
│   ├── proposal-template.md            # クライアント提案書テンプレート
│   ├── content-calendar.md             # 30日間コンテンツカレンダー
│   └── launch-checklist.md             # ローンチチェックリスト
│
├── install.sh                          # ワンコマンドインストーラー
├── uninstall.sh                        # クリーンアンインストーラー
├── requirements.txt                    # Python依存関係
└── LICENSE                             # MITライセンス
```

---

## スコアリング方法論

完全なマーケティング監査では、ウェブサイトを6つの次元でスコアリングします:

| カテゴリ | 重み | 測定内容 |
|----------|--------|------------------|
| コンテンツ・メッセージング | 25% | コピー品質、バリュープロポジション、見出し、CTA |
| コンバージョン最適化 | 20% | ファネル、フォーム、社会的証明、摩擦、緊急性 |
| SEO・検索露出 | 20% | オンページSEO、テクニカルSEO、コンテンツ構造 |
| 競合ポジショニング | 15% | 差別化、市場認知、代替製品への対応 |
| ブランド・信頼性 | 10% | デザイン品質、信頼シグナル、権威性 |
| 成長・戦略 | 10% | 価格設定、獲得チャネル、リテンション |

**総合マーケティングスコア** = 全カテゴリの加重平均（0〜100点）

---

## 仕組み

1. **コマンドを入力する** — 例: `/market audit https://example.com`
2. **Claudeがスキルファイルを読み込む** — サイトの分析方法が正確に記述されています
3. **5つのサブエージェントが並列起動** — それぞれが異なる次元を分析します
4. **Pythonスクリプトが実行される** — 自動ページ分析、競合スキャン
5. **結果が集計される** — スコア付き、優先度別、実行可能なレポートとして
6. **出力が保存される** — MarkdownファイルまたはプロフェッショナルなPDFとして

---

## ユースケース

### 代理店ビルダー向け
- 営業前に見込み客のウェブサイトに `/market audit` を実行する
- 具体的な発見事項と価格を含む `/market proposal` を生成する
- プロフェッショナルなクライアント成果物として `/market report-pdf` を納品する

### ソロプレナー向け
- `/market copy` を使って自分のランディングページを最適化する
- 製品ローンチ用に `/market emails` を生成する
- 継続的な投稿のために `/market social` カレンダーを作成する

### コンテンツクリエイター向け
- `/market competitors` で競合他社をリサーチする
- `/market launch` でローンチを計画する
- `/market funnel` でファネルを分析する

---

## アンインストール

```bash
./uninstall.sh
```

または手動で:
```bash
rm -rf ~/.claude/skills/market*
rm -f ~/.claude/agents/market-*.md
```

---

---

## ライセンス

MITライセンス — 詳細は [LICENSE](LICENSE) をご覧ください。
