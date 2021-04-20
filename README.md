# Exchange Server 漏洞攻擊
## 駭客使用此漏洞的行為
 - https://www.volexity.com/blog/2021/03/02/active-exploitation-of-microsoft-exchange-zero-day-vulnerabilities/
 - 引用自volexity網站對於此次Exchange Server漏洞做的研究

Volexity發現大量數據發送到IP地址，該地址被認為與使用用戶無關。從Exchange服務器對IIS日誌進行的仔細檢查發現，日誌顯示對與圖像，JavaScript，級聯樣式表和Outlook Web Access（OWA）使用的字體相關的有效文件的入站POST請求。最初懷疑服務器可能是後門的，並且Webshell是通過惡意HTTP模塊或ISAPI篩選器執行的。結果，Volexity開始了事件響應工作，並獲取了系統內存（RAM）和其他磁盤工件，以進行法醫調查。這項調查表明，這些服務器沒有後門，並發現了在野外使用的零日漏洞。

### 個人觀點推測

推測是可以跳過使用Exchange Server的輸入帳密，等於是繞過安全門可以直接存取內部資源，或獲取使用者email及使用紀錄。
而使用Exchange Server的單位多為政府組織及大型商業組織，這些內部的機密訊息可以完全知道商業機密或是當地政府的政令等，足以影響當地政府或是該產業的動向。
此漏洞已被中國政府的駭客組織Hafnium使用，被放入Webshell自動入侵的後門程式；自該事件通報到修補的時間以隔兩個月，無法想像他們已經掌握了多少資訊。
