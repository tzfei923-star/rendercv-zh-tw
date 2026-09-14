# RenderCV 繁體中文工作台（非官方 fork）

面向台灣求職者的繁體中文延伸專案，以官方 **v2.8** 為相容基準。

A Traditional Chinese extension for job seekers in Taiwan, using official **v2.8** as its compatibility baseline.

**已新增：** [繁體中文入門與維護說明](README.zh-TW.md)、[虛構中文履歷範例](examples/zh-TW/Example_CV.yaml)。

**Available:** [Traditional Chinese getting-started and maintenance guide](README.zh-TW.md), and a [fictional Chinese CV example](examples/zh-TW/Example_CV.yaml).

**規劃中，尚未提供：** 中文表單、YAML 匯入匯出介面、PDF 預覽及職缺版本管理。

**Planned, not yet available:** Chinese forms, a YAML import/export interface, PDF previews, and job-specific CV version management.

Forked from [rendercv/rendercv](https://github.com/rendercv/rendercv), by Sina Atalay and contributors. Git history and the original [MIT license](LICENSE) are preserved. This is an unofficial extension, not an official RenderCV localization. Rendering and validation come from upstream RenderCV; this fork currently adds documentation and examples.

本專案 fork 自 Sina Atalay 與貢獻者開發的 [rendercv/rendercv](https://github.com/rendercv/rendercv)，保留 Git 歷史與原始 [MIT 授權](LICENSE)。這是非官方延伸專案，並非 RenderCV 官方中文版本。生成與驗證功能來自上游 RenderCV；目前本 fork 新增的是說明文件與範例。

中文開發分支為 `zh-tw`，`main` 保留作為上游對照。以下保留原始英文 README。

The Chinese development branch is `zh-tw`; `main` is retained for comparison with upstream. The original English README is preserved below, with Traditional Chinese translations added alongside it.

以下採英文原文搭配繁體中文對照；指令、YAML 欄位名稱、圖片及連結維持原樣。

---

<div align="center">
<h1>RenderCV</h1>

_Resume builder for academics and engineers, deployed at [rendercv.com](https://rendercv.com)_

_為學術工作者與工程師設計的履歷產生工具，服務網站為 [rendercv.com](https://rendercv.com)。_

[![test](https://github.com/rendercv/rendercv/actions/workflows/test.yaml/badge.svg?branch=main)](https://github.com/rendercv/rendercv/actions/workflows/test.yaml)
[![coverage](https://coverage-badge.samuelcolvin.workers.dev/rendercv/rendercv.svg)](https://coverage-badge.samuelcolvin.workers.dev/redirect/rendercv/rendercv)
[![docs](<https://img.shields.io/badge/docs-mkdocs-rgb(0%2C79%2C144)>)](https://docs.rendercv.com)
[![pypi-version](<https://img.shields.io/pypi/v/rendercv?label=PyPI%20version&color=rgb(0%2C79%2C144)>)](https://pypi.python.org/pypi/rendercv)
[![pypi-downloads](<https://img.shields.io/pepy/dt/rendercv?label=PyPI%20downloads&color=rgb(0%2C%2079%2C%20144)>)](https://pypistats.org/packages/rendercv)

</div>

Write your CV or resume as YAML, then run RenderCV,

以 YAML 撰寫履歷內容，接著執行 RenderCV：

```bash
rendercv render John_Doe_CV.yaml
```

and get a PDF with perfect typography.

即可產生排版精緻的 PDF 履歷。

With RenderCV, you can:

使用 RenderCV，你可以：

- Version-control your CV — it's just text.
  <br>以版本控制管理履歷：內容以純文字保存。
- Focus on content — don't worry about the formatting.
  <br>專注於內容撰寫，讓工具處理排版。
- Get perfect typography — consistent alignment and spacing, handled for you.
  <br>產生精緻版面，由工具統一處理對齊與間距。

A YAML file like this:

例如以下 YAML 檔案：

```yaml
cv:
  name: John Doe
  location: San Francisco, CA
  email: john.doe@email.com
  website: https://rendercv.com/
  social_networks:
    - network: LinkedIn
      username: rendercv
    - network: GitHub
      username: rendercv
  sections:
    Welcome to RenderCV:
      - RenderCV reads a CV written in a YAML file, and generates a PDF with professional typography.
      - See the [documentation](https://docs.rendercv.com) for more details.
    education:
      - institution: Princeton University
        area: Computer Science
        degree: PhD
        date:
        start_date: 2018-09
        end_date: 2023-05
        location: Princeton, NJ
        summary:
        highlights:
          - "Thesis: Efficient Neural Architecture Search for Resource-Constrained Deployment"
          - "Advisor: Prof. Sanjeev Arora"
          - NSF Graduate Research Fellowship, Siebel Scholar (Class of 2022)
    ...
```

becomes one of these PDFs. Click on the images to preview.

可以生成下列不同主題的 PDF。點擊圖片即可預覽。

| [![Classic Theme Example of RenderCV](https://raw.githubusercontent.com/rendercv/rendercv/main/docs/assets/images/examples/classic.png)](https://github.com/rendercv/rendercv/blob/main/examples/John_Doe_ClassicTheme_CV.pdf) | [![Engineeringresumes Theme Example of RenderCV](https://raw.githubusercontent.com/rendercv/rendercv/main/docs/assets/images/examples/engineeringresumes.png)](https://github.com/rendercv/rendercv/blob/main/examples/John_Doe_EngineeringresumesTheme_CV.pdf) | [![Sb2nov Theme Example of RenderCV](https://raw.githubusercontent.com/rendercv/rendercv/main/docs/assets/images/examples/sb2nov.png)](https://github.com/rendercv/rendercv/blob/main/examples/John_Doe_Sb2novTheme_CV.pdf) |
| --- | --- | --- |
| [![Moderncv Theme Example of RenderCV](https://raw.githubusercontent.com/rendercv/rendercv/main/docs/assets/images/examples/moderncv.png)](https://github.com/rendercv/rendercv/blob/main/examples/John_Doe_ModerncvTheme_CV.pdf) | [![Engineeringclassic Theme Example of RenderCV](https://raw.githubusercontent.com/rendercv/rendercv/main/docs/assets/images/examples/engineeringclassic.png)](https://github.com/rendercv/rendercv/blob/main/examples/John_Doe_EngineeringclassicTheme_CV.pdf) | [![Harvard Theme Example of RenderCV](https://raw.githubusercontent.com/rendercv/rendercv/main/docs/assets/images/examples/harvard.png)](https://github.com/rendercv/rendercv/blob/main/examples/John_Doe_HarvardTheme_CV.pdf) |
| [![Ink Theme Example of RenderCV](https://raw.githubusercontent.com/rendercv/rendercv/main/docs/assets/images/examples/ink.png)](https://github.com/rendercv/rendercv/blob/main/examples/John_Doe_InkTheme_CV.pdf) | [![Opal Theme Example of RenderCV](https://raw.githubusercontent.com/rendercv/rendercv/main/docs/assets/images/examples/opal.png)](https://github.com/rendercv/rendercv/blob/main/examples/John_Doe_OpalTheme_CV.pdf) | [![Ember Theme Example of RenderCV](https://raw.githubusercontent.com/rendercv/rendercv/main/docs/assets/images/examples/ember.png)](https://github.com/rendercv/rendercv/blob/main/examples/John_Doe_EmberTheme_CV.pdf) |


## JSON Schema

**JSON Schema｜資料結構描述**

RenderCV's JSON Schema lets you fill out the YAML interactively, with autocompletion and inline documentation.

RenderCV 的 JSON Schema 可在支援的編輯器中提供自動完成與欄位說明，協助你互動式填寫 YAML。

![JSON Schema of RenderCV](https://raw.githubusercontent.com/rendercv/rendercv/main/docs/assets/images/json_schema.gif)


## Extensive Design Options

**豐富的排版設定**

You have full control over every detail.

你可以調整版面的各項細節。

```yaml
design:
  theme: classic
  page:
    size: us-letter
    top_margin: 0.7in
    bottom_margin: 0.7in
    left_margin: 0.7in
    right_margin: 0.7in
    show_footer: true
    show_top_note: true
  colors:
    body: rgb(0, 0, 0)
    name: rgb(0, 79, 144)
    headline: rgb(0, 79, 144)
    connections: rgb(0, 79, 144)
    section_titles: rgb(0, 79, 144)
    links: rgb(0, 79, 144)
    footer: rgb(128, 128, 128)
    top_note: rgb(128, 128, 128)
  typography:
    line_spacing: 0.6em
    alignment: justified
    date_and_location_column_alignment: right
    font_family: Source Sans 3
  # ...and much more
```

![Design Options of RenderCV](https://raw.githubusercontent.com/rendercv/rendercv/main/docs/assets/images/design_options.gif)

> [!TIP]
> Want to set up a live preview environment like the one shown above? See [how to set up VS Code for RenderCV](https://docs.rendercv.com/user_guide/how_to/set_up_vs_code_for_rendercv).
>
> 想建立如上圖所示的即時預覽環境，請參考 [RenderCV 的 VS Code 設定教學](https://docs.rendercv.com/user_guide/how_to/set_up_vs_code_for_rendercv)。

## Strict Validation

**嚴謹的資料驗證**

No surprises. If something's wrong, you'll know exactly what and where. If it's valid, you get a perfect PDF.

資料有誤時，工具會指出錯誤內容及位置；通過驗證後，即可產生排版完整的 PDF。

![Strict Validation Feature of RenderCV](https://raw.githubusercontent.com/rendercv/rendercv/main/docs/assets/images/validation.gif)


## Any Language

**多語言支援**

Fill out the locale field for your language.

在 `locale` 欄位設定所需語言及日期等顯示文字。

```yaml
locale:
  language: english
  last_updated: Last updated in
  month: month
  months: months
  year: year
  years: years
  present: present
  month_abbreviations:
    - Jan
    - Feb
    - Mar
  ...
```

## AI Agent Skill

**AI 助理技能**

Let AI coding agents create and edit your CV. Install the RenderCV skill:

你可以讓 AI 程式助理建立與編輯履歷。安裝 RenderCV 技能：

```bash
npx skills add rendercv/rendercv-skill
```

Works with any AI agent that supports the [skills standard](https://skills.sh). The skill is [auto-generated](https://github.com/rendercv/rendercv/blob/main/scripts/rendercv_skill/generate.py) from RenderCV's source code and [evaluated](https://github.com/rendercv/rendercv/tree/main/scripts/rendercv_skill/evals) with promptfoo against RenderCV's own Pydantic validation pipeline. See the [documentation](https://docs.rendercv.com/user_guide/how_to/use_the_ai_agent_skill) for details.

此技能適用於支援 [skills 標準](https://skills.sh) 的 AI 助理，由 RenderCV 原始碼[自動生成](https://github.com/rendercv/rendercv/blob/main/scripts/rendercv_skill/generate.py)，並透過 promptfoo 搭配 RenderCV 本身的 Pydantic 驗證流程進行[評估](https://github.com/rendercv/rendercv/tree/main/scripts/rendercv_skill/evals)。詳情請見[使用文件](https://docs.rendercv.com/user_guide/how_to/use_the_ai_agent_skill)。

## Get Started

**開始使用**

> 本節保留上游安裝指令，未固定套件版本。若要使用本 fork 的 v2.8 相容基準，請依照[繁體中文入門說明](README.zh-TW.md#快速開始)操作。
>
> This section preserves upstream's unpinned installation command. To use this fork's v2.8 compatibility baseline, follow the [Traditional Chinese getting-started guide](README.zh-TW.md#快速開始).

Install RenderCV (Requires Python 3.12+):

安裝 RenderCV（需要 Python 3.12 以上版本）：

```
pip install "rendercv[full]"
```

Create a new CV yaml file:

建立新的履歷 YAML 檔案：

```
rendercv new "John Doe"
```

Edit the YAML, then render:

編輯 YAML 內容後，執行下列指令生成履歷：

```
rendercv render "John_Doe_CV.yaml"
```

For more details, see the [user guide](https://docs.rendercv.com/user_guide/).

更多詳細說明，請參考[使用者指南](https://docs.rendercv.com/user_guide/)。
