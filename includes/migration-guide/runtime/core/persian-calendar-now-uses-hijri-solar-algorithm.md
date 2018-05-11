### <a name="persian-calendar-now-uses-the-hijri-solar-algorithm"></a><span data-ttu-id="4b011-101">Farsça Takvim şimdi Hicri Güneş enerjisi algoritması kullanır</span><span class="sxs-lookup"><span data-stu-id="4b011-101">Persian calendar now uses the Hijri solar algorithm</span></span>

|   |   |
|---|---|
|<span data-ttu-id="4b011-102">Ayrıntılar</span><span class="sxs-lookup"><span data-stu-id="4b011-102">Details</span></span>|<span data-ttu-id="4b011-103">.NET Framework 4.6 ile başlayan <xref:System.Globalization.PersianCalendar?displayProperty=name> sınıfı Hicri Güneş enerjisi algoritması kullanır.</span><span class="sxs-lookup"><span data-stu-id="4b011-103">Starting with the .NET Framework 4.6, the <xref:System.Globalization.PersianCalendar?displayProperty=name> class uses the Hijri solar algorithm.</span></span> <span data-ttu-id="4b011-104">Tarihleri arasında dönüştürme <xref:System.Globalization.PersianCalendar?displayProperty=name> ve diğer takvimlerdeki biraz farklı sonuç ile başlayan bir .NET Framework 4.6 tarih 1800'den önceki veya daha sonraki bir 2023 (Gregoryen) oluşturabilir. Ayrıca, <xref:System.Globalization.PersianCalendar.MinSupportedDateTime> artık <code>March 22, 0622 instead of March 21, 0622</code>.</span><span class="sxs-lookup"><span data-stu-id="4b011-104">Converting dates between the <xref:System.Globalization.PersianCalendar?displayProperty=name> and other calendars may produce a slightly different result beginning with the .NET Framework 4.6 for dates earlier than 1800 or later than 2023 (Gregorian).Also, <xref:System.Globalization.PersianCalendar.MinSupportedDateTime> is now <code>March 22, 0622 instead of March 21, 0622</code>.</span></span>|
|<span data-ttu-id="4b011-105">Öneri</span><span class="sxs-lookup"><span data-stu-id="4b011-105">Suggestion</span></span>|<span data-ttu-id="4b011-106">Bazı erken ve geç tarihleri PersianCalendar .NET 4.6 kullanırken biraz farklı olabileceğini unutmayın.</span><span class="sxs-lookup"><span data-stu-id="4b011-106">Be aware that some early or late dates may be slightly different when using the PersianCalendar in .NET 4.6.</span></span> <span data-ttu-id="4b011-107">(Bu değerler farklı olabileceğinden) ayrıca, tarih farklı .NET Framework sürümleri üzerinde çalışabilir işlemleri arasındaki seri hale getirme, bunları PersianCalendar tarih dizeleri olarak depolamayın.</span><span class="sxs-lookup"><span data-stu-id="4b011-107">Also, when serializing dates between processes which may run on different .NET Framework versions, do not store them as PersianCalendar date strings (since those values may be different).</span></span>|
|<span data-ttu-id="4b011-108">Kapsam</span><span class="sxs-lookup"><span data-stu-id="4b011-108">Scope</span></span>|<span data-ttu-id="4b011-109">Küçük</span><span class="sxs-lookup"><span data-stu-id="4b011-109">Minor</span></span>|
|<span data-ttu-id="4b011-110">Sürüm</span><span class="sxs-lookup"><span data-stu-id="4b011-110">Version</span></span>|<span data-ttu-id="4b011-111">4.6</span><span class="sxs-lookup"><span data-stu-id="4b011-111">4.6</span></span>|
|<span data-ttu-id="4b011-112">Tür</span><span class="sxs-lookup"><span data-stu-id="4b011-112">Type</span></span>|<span data-ttu-id="4b011-113">Çalışma zamanı</span><span class="sxs-lookup"><span data-stu-id="4b011-113">Runtime</span></span>|
|<span data-ttu-id="4b011-114">Etkilenen API'leri</span><span class="sxs-lookup"><span data-stu-id="4b011-114">Affected APIs</span></span>|<ul><li><xref:System.Globalization.PersianCalendar?displayProperty=nameWithType></li></ul>|
