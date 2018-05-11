### <a name="the-replace-method-in-odata-urls-is-disabled-by-default"></a><span data-ttu-id="30daa-101">OData URL'lerinde Değiştir yöntemi varsayılan olarak devre dışıdır</span><span class="sxs-lookup"><span data-stu-id="30daa-101">The Replace method in OData URLs is disabled by default</span></span>

|   |   |
|---|---|
|<span data-ttu-id="30daa-102">Ayrıntılar</span><span class="sxs-lookup"><span data-stu-id="30daa-102">Details</span></span>|<span data-ttu-id="30daa-103">OData URL'lerinde Değiştir yöntemi, .NET Framework 4. 5 ' başlayarak, varsayılan olarak devre dışıdır.</span><span class="sxs-lookup"><span data-stu-id="30daa-103">Beginning in the .NET Framework 4.5, the Replace method in OData URLs is disabled by default.</span></span> <span data-ttu-id="30daa-104">OData Değiştir (varsayılan olarak şimdi) devre dışı bırakıldığında (nadir bir durumdur) Değiştir işlevlerini de dahil olmak üzere kullanıcı isteklerinin başarısız olur.</span><span class="sxs-lookup"><span data-stu-id="30daa-104">When OData Replace is disabled (now by default), any user requests including replace functions (which are uncommon) will fail.</span></span>|
|<span data-ttu-id="30daa-105">Öneri</span><span class="sxs-lookup"><span data-stu-id="30daa-105">Suggestion</span></span>|<span data-ttu-id="30daa-106">Replace yöntemi gerekiyorsa (olduğu nadir bir durumdur), yapılandırma ayarları aracılığıyla yeniden etkin olabilir (<xref:System.Data.Services.Configuration.DataServicesFeaturesSection.ReplaceFunction?displayProperty=name>).</span><span class="sxs-lookup"><span data-stu-id="30daa-106">If the replace method is required (which is uncommon), it can be re-enabled through a config settings (<xref:System.Data.Services.Configuration.DataServicesFeaturesSection.ReplaceFunction?displayProperty=name>).</span></span> <span data-ttu-id="30daa-107">Ancak, bir etkin Değiştir yöntemi güvenlik açıkları açabilir ve yalnızca inceledikten sonra kullanılmalıdır.</span><span class="sxs-lookup"><span data-stu-id="30daa-107">However, an enabled replace method can open security vulnerabilities and should only be used after careful review.</span></span>|
|<span data-ttu-id="30daa-108">Kapsam</span><span class="sxs-lookup"><span data-stu-id="30daa-108">Scope</span></span>|<span data-ttu-id="30daa-109">Kenar</span><span class="sxs-lookup"><span data-stu-id="30daa-109">Edge</span></span>|
|<span data-ttu-id="30daa-110">Sürüm</span><span class="sxs-lookup"><span data-stu-id="30daa-110">Version</span></span>|<span data-ttu-id="30daa-111">4,5</span><span class="sxs-lookup"><span data-stu-id="30daa-111">4.5</span></span>|
|<span data-ttu-id="30daa-112">Tür</span><span class="sxs-lookup"><span data-stu-id="30daa-112">Type</span></span>|<span data-ttu-id="30daa-113">Çalışma zamanı</span><span class="sxs-lookup"><span data-stu-id="30daa-113">Runtime</span></span>|
|<span data-ttu-id="30daa-114">Etkilenen API'leri</span><span class="sxs-lookup"><span data-stu-id="30daa-114">Affected APIs</span></span>|<ul><li><xref:System.Data.Services.DataService%601?displayProperty=nameWithType></li></ul>|
