---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '270'
ht-degree: 6%
---
# MemoryBuffer （類別）

代表儲存在記憶體中的二進位內容。

是中間物件，可處理檔案間的資料。

## 方法

| 方法 | 說明 |
| --- | --- |
| [處置](m-memorybuffer-dispose.md) | 釋放物件使用的資源。 |
| [載入](m-memorybuffer-load.md) | 將檔案的內容載入緩衝區。 |
| [儲存](m-memorybuffer-save.md) | 將緩衝區的內容儲存到檔案。 |
| [toXML](m-memorybuffer-toxml.md) | 傳回從[MemoryBuffer](c-memorybuffer.md)的內容取得的XML JavaScript物件。 此函式已過時，請使用[toDocument()](m-memorybuffer-todocument.md) |
| [toDocument](m-memorybuffer-todocument.md) | 從此緩衝區的文字內容傳回XML檔案。 |
| [toString](m-memorybuffer-tostring.md) | 傳回字元字串形式的[MemoryBuffer](c-memorybuffer.md)的內容。 |
| [fromString](m-memorybuffer-fromstring.md) | 在緩衝區中載入字元字串的內容。 |
| [toBase64](m-memorybuffer-tobase64.md) | 轉換以base 64編碼的緩衝區或字元字串的一部分。 |
| [appendBase64](m-memorybuffer-appendbase64.md) | 將資料從以base 64編碼的字元字串附加至緩衝區的結尾。 |
| [removeAll](m-memorybuffer-removeall.md) | 排清緩衝區。 |
| [sha1](m-memorybuffer-sha1.md) | 計算MemoryBuffer內容的SHA-1簽名。 |
| [sha224](m-memorybuffer-sha224.md) | 計算MemoryBuffer內容的SHA-2 224位元簽章。 |
| [sha256](m-memorybuffer-sha256.md) | 計算MemoryBuffer內容的SHA-2 256位元簽章。 |
| [sha384](m-memorybuffer-sha384.md) | 計算MemoryBuffer內容的SHA-2 384位元簽章。 |
| [sha512](m-memorybuffer-sha512.md) | 計算MemoryBuffer內容的SHA-2 512位元簽章。 |
| [fromHexString](m-memorybuffer-fromhexstring.md) | 在緩衝區中載入十六進位字串的內容。 |
| [toHexString](m-memorybuffer-tohexstring.md) | 將緩衝區轉換為十六進位字元字串。 |
| [hmac](m-memorybuffer-hmac.md) | 計算緩衝區的MD5、SHA-1或SHA-256雜湊。 |

## 屬性

| 屬性 | 說明 |
| --- | --- |
| [大小](p-memorybuffer-size.md) | 傳回緩衝區的大小（位元組）。 |
| [isEmpty](p-memorybuffer-isempty.md) | 如果緩衝區是空的，則傳回true。 |

## 功能

**可用於：**

* 內容管理
* 傳遞屬性
* 傳遞訊息
* 類型規則
* 匯入
* JSSP
* SOAP方法
* WebApp
* 工作流程
