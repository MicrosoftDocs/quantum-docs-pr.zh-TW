# <a name="articles"></a>文章

在此目錄中，您可以找到「量子開發工具組」檔的相關文章。 此目錄包含：

- **文章目錄**：包含檔中每個區段的文章。 在這些目錄中，您可以找到下列內容：
  
  - 每個目錄都包含一個檔案 `toc.yml` ，以在主要目錄（TOC）中顯示目錄的內容。
  - 包含檔的 Markdown 文章。 這些文章應遵循[Microsoft Docs 參與者指南](https://docs.microsoft.com/en-us/contribute/)的指導方針。
  - 文章子目錄。 這些子目錄也應該包含自己的檔案 `toc.yml` 。

> :p encil：雖然可以 `*.md` 直接在父檔案中參考檔案 `TOC.yml` ，但若要讓專案排序，我們只會從其目前目錄的中參考它們 `toc.yml` 。

- **主要目錄（TOC） `TOC.yml` **檔案：在此檔案中，網站目錄的區段會與 `toc.yml` 每個區段目錄之主要檔案的參考一起列出。
- **`index.yml`** YAML，並提供檔登陸頁面的設定。
- **`\media`**：用來儲存檔中所使用之所有影像的目錄。 它包含用 `\media\src` 來儲存影像來源檔案的子目錄。
- **授權檔案**：包含合法授權的檔案
- **技術**檔案：包含宏和中繼資料的檔案。

## <a name="guidelines"></a>指導方針

有關此目錄的參與者組織的一些一般指導方針：

- 每個目錄或子目錄都應該包含自己的檔案， `toc.yml` 其中參考的是相同層級的發行項或其子目錄的檔案 `toc.yml` 。
- 存放庫目錄的組織應該盡可能接近檔網站目錄的組織結構（英文）。
- 所有影像都應該儲存在中 `articles\media` ，而不是在 [發行項] 資料夾中。
- 發行項的標題、目錄中的名稱，以及中繼資料的*uid*應該盡可能接近它們，並且清楚地表示 Markdown 檔的 H1 標頭。

## <a name="adding-images"></a>新增影像

若要在深色模式中正確轉譯影像，您必須避免使用透明度。
- 針對檔案 `*.jpg` ，您不需要執行任何動作，因為檔案格式不支援透明元素。
- 針對檔案 `*.png` ，您必須加入白色背景，或將 Alpha 色板的值變更為100。 在 Windows 中執行此動作的最簡單方式，是在 [繪製並儲存] 中開啟檔案，並覆寫原始檔案。
- 針對檔案 `*.svg` ，您必須在最低層中新增白色矩形。 您可以使用引導 inkscape 來執行此動作：
  - 開啟 `*.svg` 檔案。
  - 選取 [方形 maker] 工具，並在原始圖表頂端繪製一個白色矩形。
  - 按一下深色箭號或按 F1 鍵，以選取工具「選取和轉換物件」。
  - 選取矩形時，按一下工具列元素中的 [下方選取範圍] （結束）。
  - 使用滑鼠或方向鍵調整矩形。