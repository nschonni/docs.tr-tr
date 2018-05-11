### <a name="chained-popups-with-staysopenfalse"></a><span data-ttu-id="9d85e-101">Açılan pencereler StaysOpen ile zincirleme = False</span><span class="sxs-lookup"><span data-stu-id="9d85e-101">Chained Popups with StaysOpen=False</span></span>

|   |   |
|---|---|
|<span data-ttu-id="9d85e-102">Ayrıntılar</span><span class="sxs-lookup"><span data-stu-id="9d85e-102">Details</span></span>|<span data-ttu-id="9d85e-103">Açılan pencere StaysOpen ile = False olması dışında açılan tıklattığınızda kapatın.</span><span class="sxs-lookup"><span data-stu-id="9d85e-103">A Popup with StaysOpen=False is supposed to close when you click outside the Popup.</span></span> <span data-ttu-id="9d85e-104">Ne zaman iki veya daha fazla tür açılan pencereler zincirleme (yani bir içeren başka bir) dahil olmak üzere birçok sorunu vardı:</span><span class="sxs-lookup"><span data-stu-id="9d85e-104">When two or more such Popups are chained (i.e. one contains another), there were many problems, including:</span></span><ul><li><span data-ttu-id="9d85e-105">İki düzey açın, P2 dışında ancak P1 içini tıklatın.</span><span class="sxs-lookup"><span data-stu-id="9d85e-105">Open two levels, click outside P2 but inside P1.</span></span>  <span data-ttu-id="9d85e-106">Hiçbir şey olmaz.</span><span class="sxs-lookup"><span data-stu-id="9d85e-106">Nothing happens.</span></span></li><li><span data-ttu-id="9d85e-107">İki düzey açın, dış P1'ı tıklatın.</span><span class="sxs-lookup"><span data-stu-id="9d85e-107">Open two levels, click outside P1.</span></span>  <span data-ttu-id="9d85e-108">Her iki tarayıcınızı kapatın.</span><span class="sxs-lookup"><span data-stu-id="9d85e-108">Both popups close.</span></span></li><li><span data-ttu-id="9d85e-109">Açın ve iki düzey kapatın.</span><span class="sxs-lookup"><span data-stu-id="9d85e-109">Open and close two levels.</span></span>  <span data-ttu-id="9d85e-110">Ardından P2 açmayı yeniden deneyin.</span><span class="sxs-lookup"><span data-stu-id="9d85e-110">Then try to open P2 again.</span></span>  <span data-ttu-id="9d85e-111">Hiçbir şey olmaz.</span><span class="sxs-lookup"><span data-stu-id="9d85e-111">Nothing happens.</span></span></li><li><span data-ttu-id="9d85e-112">Üç düzeyden açmayı deneyin.</span><span class="sxs-lookup"><span data-stu-id="9d85e-112">Try to open three levels.</span></span>  <span data-ttu-id="9d85e-113">Yapamazsınız.</span><span class="sxs-lookup"><span data-stu-id="9d85e-113">You can't.</span></span>  <span data-ttu-id="9d85e-114">(Hiçbir şey olmaz veya tıklattığınız bağlı olarak ilk iki düzey kapatın.) Bu gibi durumlarda (ve diğer çeşitleri) artık beklendiği gibi çalışmayabilir.</span><span class="sxs-lookup"><span data-stu-id="9d85e-114">(Either nothing happens or the first two levels close, depending on where you click.) These cases (and other variants) now work as expected.</span></span></li></ul>|
|<span data-ttu-id="9d85e-115">Kapsam</span><span class="sxs-lookup"><span data-stu-id="9d85e-115">Scope</span></span>|<span data-ttu-id="9d85e-116">Kenar</span><span class="sxs-lookup"><span data-stu-id="9d85e-116">Edge</span></span>|
|<span data-ttu-id="9d85e-117">Sürüm</span><span class="sxs-lookup"><span data-stu-id="9d85e-117">Version</span></span>|<span data-ttu-id="9d85e-118">4.7.1</span><span class="sxs-lookup"><span data-stu-id="9d85e-118">4.7.1</span></span>|
|<span data-ttu-id="9d85e-119">Tür</span><span class="sxs-lookup"><span data-stu-id="9d85e-119">Type</span></span>|<span data-ttu-id="9d85e-120">Çalışma zamanı</span><span class="sxs-lookup"><span data-stu-id="9d85e-120">Runtime</span></span>|
|<span data-ttu-id="9d85e-121">Etkilenen API'leri</span><span class="sxs-lookup"><span data-stu-id="9d85e-121">Affected APIs</span></span>|<ul><li><xref:System.Windows.Controls.Primitives.Popup.StaysOpen?displayProperty=nameWithType></li></ul>|
