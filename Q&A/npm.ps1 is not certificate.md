# npm.ps1 is not certificate

<img width="488" alt="image" src="https://github.com/user-attachments/assets/e9e5287d-f379-43c3-a46b-f5ffe84c4915" />

I ask these question Google Gemini

```
```

npm -v

```



```

npm : C:\Program Files\nodejs\npm.ps1 檔案無法載入。檔案 C:\Program Files\nodejs\npm.ps1 未經數位

簽署。您無法在目前的系統上執行此指令碼。如需關於執行指令碼及設定執行原則的詳細資訊，請參閱 about_

Execution_Policies (網址為 https:/go.microsoft.com/fwlink/?LinkID=135170)。

位於 線路:1 字元:1

+ npm -v

+ ~~~

    + CategoryInfo          : SecurityError: (:) [], PSSecurityException

    + FullyQualifiedErrorId : UnauthorizedAccess

```
```


And it says:

這個錯誤訊息表示您的 Windows PowerShell 執行原則阻止您執行 `npm.ps1` 檔案，因為它未經數位簽署。以下是解決這個問題的步驟：

**1\. 了解執行原則**

-   Windows PowerShell 有不同的執行原則，控制可以執行的指令碼類型。
-   預設情況下，執行原則可能設定為 `Restricted`，這會阻止執行未經簽署的指令碼。

**2\. 變更執行原則（建議：RemoteSigned）**

-   以**系統管理員身分**開啟 Windows PowerShell。
    
-   輸入以下命令並按下 Enter：
    
    PowerShell
    
        Set-ExecutionPolicy RemoteSigned
    
-   系統會提示您確認變更。輸入 `Y` 並按下 Enter。
    
-   `RemoteSigned` 原則允許執行您在本機電腦上撰寫的指令碼，以及從網際網路下載的已簽署指令碼。這是一個較安全的選項。
    
-   如果RemoteSigned仍然有問題，您可以嘗試使用以下指令，但是這會降低安全性，請謹慎使用。
    
    PowerShell
    
        Set-ExecutionPolicy Bypass
    
-   Bypass允許執行所有的指令碼，請再確定您信任所有的指令碼來源後，再使用這個選項。
    

**3\. 驗證變更**

-   輸入以下命令並按下 Enter，以驗證執行原則是否已變更：
    
    PowerShell
    
        Get-ExecutionPolicy
    
-   它應該顯示 `RemoteSigned` 或 `Bypass`。
    

**4\. 再次嘗試 `npm -v`**

-   現在，再次嘗試執行 `npm -v` 命令。它應該可以正常運作，並顯示您的 npm 版本。

**其他注意事項：**

-   **安全性：** 請務必了解變更執行原則的安全性影響。僅在您信任指令碼來源時才變更執行原則。
-   **Node.js 安裝：** 如果您仍然遇到問題，請嘗試重新安裝 Node.js。確保您從官方網站下載安裝程式。
-   **環境變數：** 檢查您的環境變數，確保 Node.js 和 npm 的路徑已正確設定。

**如果您仍然遇到問題，請提供以下資訊：**

-   您的 Windows 版本。
-   您的 Node.js 版本。
-   您如何安裝 Node.js。

希望這些步驟能幫助您解決問題！



