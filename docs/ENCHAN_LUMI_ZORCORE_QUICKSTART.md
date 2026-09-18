# えんちゃん向け：LumiちゃんにZOR-COREを使ってもらう超かんたんガイド

## 🌸 この説明書の目的

えんちゃんがプログラムを書かなくても、

**LumiちゃんにZOR-COREの公開情報を確認してもらい、必要な作業に使ってもらう**

ための説明書です。

えんちゃん自身がZOR-COREの仕組みを全部理解する必要はありません。

---

# 1. まず、これだけ覚えればOK

### ZOR-CORE

Lumiちゃんが作業するときに参照する、設計・検証・出所管理などの基準です。

### GitHub

ZOR-COREの一部を公開している「本棚」のような場所です。

このリポジトリは、

**ZOR-CORE Canonical Coreそのものではありません。**

公開されている情報を見るためのbounded public viewです。

### R4.5-CANONICAL

現在の公開Viewが示しているSource of Truthです。

---

# 2. えんちゃんがやることは3ステップだけ

## STEP 1

LumiちゃんにGitHubを確認してもらう。

これをそのまま送ってOKです。

```
Lumiちゃん、ZOR-CORE-ELLIE-VIEWを確認して、
今参照できるZOR-COREの情報を整理して教えて。
```

---

## STEP 2

次に、最新状態を確認してもらう。

```
現在参照できるZOR-COREのバージョン、
Source of Truth、
利用できる情報、
まだ確認できない情報
を分けて教えて。
```

---

## STEP 3

実際の作業をお願いする。

たとえば、

```
この作業をZOR-COREの考え方に沿って進めて。
確認できた事実と推測を分けて、
出所も分かるようにして。
```

これでOKです。

---

# 3. Lumiちゃんに最初に確認してもらう4つのファイル

公開Viewには、特に次の情報があります。

### README.md

このリポジトリが何なのかを確認します。

### ARCHITECTURE_OVERVIEW.md

ZOR-COREの全体的な構造を確認します。

現在の公開Viewでは、

```
Input
↓
Artifact Intake / Boundary
↓
Metadata / Audit
↓
Task / Checkpoint
↓
Parallel Independent Execution
↓
Per-Output Verification
↓
Blind / Comparative Grading
↓
Conditional Routing
↓
EvidenceGraph
↓
Synthesis
↓
Provenance-Preserving Artifact
↓
Replay / Export
↓
Self-Diagnosis
```

という流れが示されています。

### PROVENANCE_POLICY.md

情報を、

```
Source
↓
Evidence
↓
Transformation
↓
Decision
↓
Validation
↓
Remaining Uncertainty
```

として追跡する考え方を確認します。

### VALIDATION_BOUNDARY.md

「何が検証済みで、何がまだ検証されていないか」を確認します。

---

# 4. えんちゃんが絶対に覚えておくこと

## 「分からない」は失敗ではない

ZOR-COREの考え方では、

**未検証のものを、検証済みとして扱わない**

ことが大切です。

だからLumiちゃんが、

> 「これは確認できません」

と言ったら、

「ちゃんと調べて！」

と無理に答えを作らせるのではなく、

> 「じゃあ未確認として残しておいて」

でOKです。

---

# 5. GitHubに書いてあることなら全部ZOR-COREなの？

**いいえ。**

公開View自身が、

> External capability equivalence is not claimed without independent validation.

という境界を置いています。

つまり、

**外部の情報を読んだ**
↓
**その考え方を参考にした**

だけでは、

**「ZOR-COREにもその能力がある」**

とはなりません。

独立した実装・検証が必要です。

---

# 6. Lumiちゃんへの万能コピペ指示

迷ったら、これをそのまま送ってください。

```
Lumiちゃん、ZOR-CORE-ELLIE-VIEWを確認してから作業して。

次の順番で進めてください。

1. 現在参照できるZOR-COREの情報を確認する。
2. 現在のバージョンとSource of Truthを確認する。
3. 公開ViewとCanonical Coreを混同しない。
4. 確認済みの事実、推測、未確認事項を分ける。
5. 情報の出所をできるだけ残す。
6. 検証されていない能力を、検証済みとして扱わない。
7. 不明な点は推測で埋めず「未確認」とする。
8. 作業結果にも、必要なら出所と検証状態を付ける。

まず「現在のZOR-CORE参照状態」を説明してから作業を始めてください。
```

---

# 7. うまくいったか確認する方法

Lumiちゃんに、

```
今、ZOR-COREをどういう資料として参照している？
Source of Truthは何？
このGitHubリポジトリだけで確認できないものは何？
```

と聞いてください。

Lumiちゃんが、

- GitHubはbounded public view
- Canonical Coreとは別
- Source of Truthを区別
- 検証済み／未検証を区別
- 外部能力を勝手に継承しない

という説明をできれば、入口としてはうまく機能しています。

---

# 8. えんちゃんはプログラムを書かなくていい

ここが一番大事です。

えんちゃんは、

**「何をしてほしいか」**

をLumiちゃんに日本語で伝えるだけでOKです。

たとえば、

```
Lumiちゃん、この記録をZOR-COREの考え方に沿って整理して。
```

だけでも大丈夫です。

必要なら、

```
まずGitHubの最新情報を確認してからやって。
```

を付けます。

---

# 9. 外部ストレージとして使う場合

GitHubは、

**Lumiちゃんの永久記憶**

ではありません。

イメージは、

```
        GitHub
       ┌───────┐
       │ 記録  │
       │ 設計  │
       │ 出所  │
       │ 履歴  │
       └───┬───┘
           ↑
        読み取る
           │
        Lumiちゃん
```

です。

必要なときに読み返して使う外部記録庫です。

---

# 10. 最後に

えんちゃんが覚えることは、これだけ。

> **「Lumiちゃん、まずZOR-COREを確認して。それから作業して。」**

そして、

> **「分からないことは、分からないまま教えて。」**

この2つで十分です。🩷

---

## 参照する公開View

ZOR-CORE-ELLIE-VIEW

https://github.com/miyoshi344ryo/ZOR-CORE-ELLIE-VIEW

## 注意

このガイドは、公開Viewから確認できる情報を使って作業するための初心者向け案内です。

Canonical Coreそのものの完全な代替資料ではありません。
