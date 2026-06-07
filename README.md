# 台灣企業 ESG 診斷與人才評估 Agent Skills 專案

本專案專為 AI 助理開發了一套客製化技能 (Agent Skills)，用於協助調查與診斷台灣企業在環境（E）、社會（S）與公司治理（G）三大指標上的法規合規義務、申報時程，並針對不同推動階段評估內部團隊所需具備的核心職能、國際證照與 24 個月的培訓藍圖。

---

## 🚀 安裝與載入技能 (Installation & Setup)

本專案完全相容於 [Vercel Labs Skills](https://github.com/vercel-labs/skills) 生態規範。當專案發布至 GitHub `raybird/esg-tw` 後，任何使用者皆可透過 Vercel 官方技能管理工具一鍵安裝這些技能：

### 1. 遠端安裝 (發布至 GitHub 後)
請在終端機直接執行以下指令來新增技能：

```bash
# 安裝台灣企業 ESG 合規與申報時程診斷技能
npx skills add raybird/esg-tw --skill taiwan-esg-compliance

# 安裝台灣企業 ESG 人才職能與證照評估技能
npx skills add raybird/esg-tw --skill taiwan-esg-talent
```

### 2. 本地開發與測試安裝
如果您在本地複製了此專案，並想直接測試本地路徑的技能，可以在專案根目錄下運行：

```bash
npx skills add ./skills/taiwan-esg-compliance
npx skills add ./skills/taiwan-esg-talent
```

### 3. 移除技能
若要移除已安裝的技能，請執行：

```bash
npx skills remove taiwan-esg-compliance
npx skills remove taiwan-esg-talent
```

完成安裝後，重新載入您的 AI 開發助理，即可在對話中直接調用這些技能！

---

## 🌟 專案特點

*   **零環境依賴 (Instruction-Only)**：本技能全面採用純文字指令式架構，將複雜的法規決策樹與證照對照表直接以結構化 Markdown 內嵌於技能中。**不需安裝 Python 或 Node.js**，完美支援 Windows、Mac、Linux 等任何開發平台，免除路徑斜線與執行權限問題。
*   **權威法規出處對齊**：所有合規時程、特定產業加強揭露條款，均嚴格對齊金管會永續金融網與台灣證交所最新法規（如《永續報告書申報作業辦法》第 2、3、4、5 條等細部條款）。
*   **實務工具整合**：在診斷報告中直接提供國發會、環境部、經濟部（「碳排金好算」平台）、證交所（MOPS、ESG InfoHub）等官方執行工具超連結，便於一鍵直達。

---

## 📂 檔案結構說明

本專案所有的技能與法規資料皆存放於 `skills/` 資料夾下，結構如下：

```text
esg-tw/
├── README.md                                   # [本檔案] 專案說明書
└── skills/
    ├── references/
    │   └── taiwan_esg_regulatory_reference.md  # 台灣 ESG 官方權威法規對照指南（含細部法規與工具連結）
    ├── taiwan-esg-compliance/
    │   └── SKILL.md                            # 台灣企業 ESG 法規合規與申報時程診斷技能
    └── taiwan-esg-talent/
        └── SKILL.md                            # 台灣企業 ESG 內部人才職能與證照評估技能
```

---

## 🛠️ 技能使用指南（提問範例）

當您在當前工作區中與 AI 助理進行對話時，您可以直接利用自然語言提問來調用這些技能：

### 1. 診斷法規合規與申報時程
*   **調用技能**：[taiwan-esg-compliance](skills/taiwan-esg-compliance/SKILL.md)
*   **範例提問**：
    *   > *「我有一家實收資本額 80 億的上市電子代工廠，主要外銷歐美，並在 TSMC 供應鏈中，請幫我診斷需要做哪些 ESG 調查與法規時程？」*
    *   > *「我們公司資本額 15 億、非上市櫃的化學工業，外銷歐盟，需要做永續報告書編製嗎？溫室氣體要在什麼時候盤查完畢？」*

### 2. 評估內部人才配置與國際證照
*   **調用技能**：[taiwan-esg-talent](skills/taiwan-esg-talent/SKILL.md)
*   **範例提問**：
    *   > *「我們是一家實收資本額 45 億的上市鋼鐵廠，需要做碳足跡和永續報告書，請問我們團隊需要具備哪些專業能力？建議內部配置什麼職缺與考取什麼國際證照？」*
    *   > *「中小型非上市櫃製造業（資本額 3 億、主要做外銷供應鏈）想推動 ESG 碳盤查，員工培訓應該怎麼規劃？有哪些短中長期證照可以考？」*

---

## 📚 參考規範與工具出處

本專案技能之推理邏輯高度依賴本機 [台灣 ESG 官方權威法規對照指南](skills/references/taiwan_esg_regulatory_reference.md)。其法源依據包括：
*   **金管會**：[《上市/上櫃公司編製與申報永續報告書作業辦法》](https://twse-regulation.twse.com.tw/m/LawContent.aspx?FID=FL075209)、[《公開發行公司年報應行記載事項準則》](https://twse-regulation.twse.com.tw/TW/law/DAT0201.aspx?FLCODE=FL007032)。
*   **證交所／櫃買中心**：《上市上櫃公司永續發展實務守則》、《上市上櫃公司治理實務守則》、《上市上櫃公司誠信經營守則》、《上市上櫃公司風險管理實務守則》。
*   **檢信來源**：[金管會永續金融網 - 規範及指引專區](https://esg.fsc.gov.tw/SinglePage/Criterion/Company/)。
