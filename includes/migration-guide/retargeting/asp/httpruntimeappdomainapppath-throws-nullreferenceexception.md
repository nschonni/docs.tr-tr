### <a name="httpruntimeappdomainapppath-throws-a-nullreferenceexception"></a><span data-ttu-id="740b3-101">NullReferenceException HttpRuntime.AppDomainAppPath oluşturur</span><span class="sxs-lookup"><span data-stu-id="740b3-101">HttpRuntime.AppDomainAppPath Throws a NullReferenceException</span></span>

|   |   |
|---|---|
|<span data-ttu-id="740b3-102">Ayrıntılar</span><span class="sxs-lookup"><span data-stu-id="740b3-102">Details</span></span>|<span data-ttu-id="740b3-103">.NET Framework 4.6.2'da, çalışma zamanı oluşturur bir <code>T:System.NullReferenceException</code> alınırken bir <code>P:System.Web.HttpRuntime.AppDomainAppPath</code> boş karakterler içeren değer. .NET Framework 4.6.1 ve önceki sürümleri, çalışma zamanı oluşturur bir <code>T:System.ArgumentNullException</code>.</span><span class="sxs-lookup"><span data-stu-id="740b3-103">In the .NET Framework 4.6.2, the runtime throws a <code>T:System.NullReferenceException</code> when retrieving a <code>P:System.Web.HttpRuntime.AppDomainAppPath</code> value that includes null characters.In the .NET Framework 4.6.1 and earlier versions, the runtime throws an <code>T:System.ArgumentNullException</code>.</span></span>|
|<span data-ttu-id="740b3-104">Öneri</span><span class="sxs-lookup"><span data-stu-id="740b3-104">Suggestion</span></span>|<span data-ttu-id="740b3-105">Bu değişiklik yanıt izleme birini yapabilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="740b3-105">You can do either of the follow to respond to this change:</span></span><ul><li><span data-ttu-id="740b3-106">Tanıtıcı <code>T:System.NullReferenceException</code> uygulama, .NET Framework 4.6.2 çalıştırıyorsa.</span><span class="sxs-lookup"><span data-stu-id="740b3-106">Handle the <code>T:System.NullReferenceException</code> if you application is running on the .NET Framework 4.6.2.</span></span></li><li><span data-ttu-id="740b3-107">Önceki davranışını geri yükler ve oluşturur .NET Framework 4.7, yükseltme bir <code>T:System.ArgumentNullException</code>.</span><span class="sxs-lookup"><span data-stu-id="740b3-107">Upgrade to the .NET Framework 4.7, which restores the previous behavior and throws an <code>T:System.ArgumentNullException</code>.</span></span></li></ul>|
|<span data-ttu-id="740b3-108">Kapsam</span><span class="sxs-lookup"><span data-stu-id="740b3-108">Scope</span></span>|<span data-ttu-id="740b3-109">Kenar</span><span class="sxs-lookup"><span data-stu-id="740b3-109">Edge</span></span>|
|<span data-ttu-id="740b3-110">Sürüm</span><span class="sxs-lookup"><span data-stu-id="740b3-110">Version</span></span>|<span data-ttu-id="740b3-111">4.6.2</span><span class="sxs-lookup"><span data-stu-id="740b3-111">4.6.2</span></span>|
|<span data-ttu-id="740b3-112">Tür</span><span class="sxs-lookup"><span data-stu-id="740b3-112">Type</span></span>|<span data-ttu-id="740b3-113">Yeniden hedefleme</span><span class="sxs-lookup"><span data-stu-id="740b3-113">Retargeting</span></span>|
|<span data-ttu-id="740b3-114">Etkilenen API'leri</span><span class="sxs-lookup"><span data-stu-id="740b3-114">Affected APIs</span></span>|<ul><li><xref:System.Web.HttpRuntime.AppDomainAppPath?displayProperty=nameWithType></li></ul>|
