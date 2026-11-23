---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 5%
---
# 執行命令

> 警告：此函式適用於內部部署環境。

執行命令並擷取錯誤代碼和標準輸出。

```text
execCommand (command [, bNoThrow ])
```

## 參數

**command**&#x200B;要與其引數一起執行的命令。

**bNoThrow** true可取得輸出和錯誤碼，即使命令未傳回零（預設為false）。

## 傳回值

傳回第一個元素對應至命令傳回碼的表格（如果傳回碼與零不同，則為異常），第二個元素則為包含產生之標準輸出的字元字串。

## 備註

如果沒有bNothrow選項，如果命令無法執行或命令執行時發生錯誤，則會引發例外狀況。 如果bNoThrow等於true，則只有在無法執行命令時才會引發例外狀況。 運運算元需要「createProcess」許可權才能使用此函式，否則會發生例外狀況。 視您的安裝而定，某些命令可能會出現在封鎖清單上。 例如：ln、dd、openssl、curl、wget、python、python3、perl、ruby、sh、bash、dash、zsh、base64、nlserver、node、phantomjs、java、awk、nc、telnet、ssh、scp、ftp。

## 範例

```text
var result = execCommand('gpg-exec.sh gpg --no-tty --yes -r CampaignOperations@adobe.com --encrypt "file_to_encrypt"', true);
```

## 功能

**可用於：**

* 內容管理
* 傳遞屬性
* 類型規則
* JSSP
* SOAP方法
* WebApp
* 工作流程
