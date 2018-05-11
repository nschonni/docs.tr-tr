### <a name="long-path-support"></a><span data-ttu-id="d8cf1-101">Uzun yol desteği</span><span class="sxs-lookup"><span data-stu-id="d8cf1-101">Long path support</span></span>

|   |   |
|---|---|
|<span data-ttu-id="d8cf1-102">Ayrıntılar</span><span class="sxs-lookup"><span data-stu-id="d8cf1-102">Details</span></span>|<span data-ttu-id="d8cf1-103">Uygulamalarla hedefleyen (en fazla karakter sayısı 32 K) .NET Framework 4.6.2, uzun yolları desteklenir ve 260 karakter başlangıç (veya <code>MAX_PATH</code>) yolu uzunlukları sınırlama kaldırıldı. .NET Framework 4.6.2 hedeflemek için derlenir uygulamaları için daha önce belirtti yolları kod bir <xref:System.IO.PathTooLongException?displayProperty=name> bir yolu aştığından 260 karakter şimdi throw bir <xref:System.IO.PathTooLongException?displayProperty=name> yalnızca aşağıdaki koşullar altında:</span><span class="sxs-lookup"><span data-stu-id="d8cf1-103">Starting with apps that target the .NET Framework 4.6.2, long paths (of up to 32K characters) are supported, and the 260-character (or <code>MAX_PATH</code>) limitation on path lengths has been removed.For apps that are recompiled to target the .NET Framework 4.6.2, code paths that previously threw a <xref:System.IO.PathTooLongException?displayProperty=name> because a path exceeded 260 characters will now throw a <xref:System.IO.PathTooLongException?displayProperty=name> only under the following conditions:</span></span><ul><li><span data-ttu-id="d8cf1-104">Yol uzunluğu değerinden daha büyük <xref:System.Int16.MaxValue> (32.767) karakter.</span><span class="sxs-lookup"><span data-stu-id="d8cf1-104">The length of the path is greater than <xref:System.Int16.MaxValue> (32,767) characters.</span></span></li><li><span data-ttu-id="d8cf1-105">İşletim sistemi döndürür <code>COR_E_PATHTOOLONG</code> ya da eşdeğer.</span><span class="sxs-lookup"><span data-stu-id="d8cf1-105">The operating system returns <code>COR_E_PATHTOOLONG</code> or its equivalent.</span></span></li></ul><span data-ttu-id="d8cf1-106">.NET Framework 4.6.1 ve önceki sürümlerini hedefleyen uygulamalar için çalışma zamanı otomatik olarak oluşturur bir <xref:System.IO.PathTooLongException?displayProperty=name> her bir yol 260 karakteri aşıyor.</span><span class="sxs-lookup"><span data-stu-id="d8cf1-106">For apps that target the .NET Framework 4.6.1 and earlier versions, the runtime automatically throws a <xref:System.IO.PathTooLongException?displayProperty=name> whenever a path exceeds 260 characters.</span></span>|
|<span data-ttu-id="d8cf1-107">Öneri</span><span class="sxs-lookup"><span data-stu-id="d8cf1-107">Suggestion</span></span>|<span data-ttu-id="d8cf1-108">.NET Framework 4.6.2 hedefleyen uygulamalar için aşağıdakileri ekleyerek arzu değilse, uzun yol desteği dışında seçebilirsiniz <code>&lt;runtime&gt;</code> bölümü, <code>app.config</code> dosyası:</span><span class="sxs-lookup"><span data-stu-id="d8cf1-108">For apps that target the .NET Framework 4.6.2, you can opt out of long path support if it is not desirable by adding the following to the <code>&lt;runtime&gt;</code> section of your <code>app.config</code> file:</span></span><pre><code class="language-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.IO.BlockLongPaths=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre><span data-ttu-id="d8cf1-109">Hedef uygulamalar için .NET Framework'ün önceki sürümlerinde, ancak .NET Framework 4.6.2 çalıştırmak veya daha sonra uzun yol desteklemek için aşağıdakileri ekleyerek kabul <code>&lt;runtime&gt;</code> bölümü, <code>app.config</code> dosyası:</span><span class="sxs-lookup"><span data-stu-id="d8cf1-109">For apps that target earlier versions of the .NET Framework but run on the .NET Framework 4.6.2 or later, you can opt in to long path support by adding the following to the <code>&lt;runtime&gt;</code> section of your <code>app.config</code> file:</span></span><pre><code class="language-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.IO.BlockLongPaths=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="d8cf1-110">Kapsam</span><span class="sxs-lookup"><span data-stu-id="d8cf1-110">Scope</span></span>|<span data-ttu-id="d8cf1-111">Küçük</span><span class="sxs-lookup"><span data-stu-id="d8cf1-111">Minor</span></span>|
|<span data-ttu-id="d8cf1-112">Sürüm</span><span class="sxs-lookup"><span data-stu-id="d8cf1-112">Version</span></span>|<span data-ttu-id="d8cf1-113">4.6.2</span><span class="sxs-lookup"><span data-stu-id="d8cf1-113">4.6.2</span></span>|
|<span data-ttu-id="d8cf1-114">Tür</span><span class="sxs-lookup"><span data-stu-id="d8cf1-114">Type</span></span>|<span data-ttu-id="d8cf1-115">Yeniden hedefleme</span><span class="sxs-lookup"><span data-stu-id="d8cf1-115">Retargeting</span></span>|
