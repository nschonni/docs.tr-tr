### <a name="wcf-services-that-use-nettcp-with-ssl-sercurity-and-md5-certificate-authentication"></a><span data-ttu-id="da817-101">SSL sercurity ve MD5 sertifika kimlik doğrulaması ile NETTCP kullanan WCF hizmetleri</span><span class="sxs-lookup"><span data-stu-id="da817-101">WCF services that use NETTCP with SSL sercurity and MD5 certificate authentication</span></span>

|   |   |
|---|---|
|<span data-ttu-id="da817-102">Ayrıntılar</span><span class="sxs-lookup"><span data-stu-id="da817-102">Details</span></span>|<span data-ttu-id="da817-103">.NET Framework 4.6 TLS 1.1 ve TLS 1.2 WCF SSL varsayılan protokol listesine ekler.</span><span class="sxs-lookup"><span data-stu-id="da817-103">The .NET Framework 4.6 adds TLS 1.1 and TLS 1.2 to the WCF SSL default protocol list.</span></span> <span data-ttu-id="da817-104">İstemci ve sunucu makinelerini .NET Framework 4.6 veya sonrası yüklü olduğunda, TLS 1.2 anlaşması için kullanılır. TLS 1.2 MD5 sertifika kimlik doğrulamasını desteklemez.</span><span class="sxs-lookup"><span data-stu-id="da817-104">When both client and server machines have the .NET Framework 4.6 or later installed, TLS 1.2 is used for negotiation.TLS 1.2 does not support MD5 certificate authentication.</span></span> <span data-ttu-id="da817-105">Sonuç olarak, bir müşteri bir MD5 sertifikası kullanıyorsa, WCF hizmetine bağlanmak WCF istemcisini başarısız olur.</span><span class="sxs-lookup"><span data-stu-id="da817-105">As a result, if a customer uses an MD5 certificate, the WCF client will fail to connect to the WCF service.</span></span><ul><li><span data-ttu-id="da817-106">[] Quirked / / kullanımı genellikle hedefleme, AppContext veya yapılandırma dosyaları çalışma zamanı özelliğini etkinleştirmek veya devre dışı bırakmak için bazı mekanizması kullanır.</span><span class="sxs-lookup"><span data-stu-id="da817-106">[ ] Quirked // Uses some mechanism to turn the feature on or off, usually using runtime targeting, AppContext or config files.</span></span> <span data-ttu-id="da817-107">Bazı durumlarda otomatik olarak açılması gerekir.</span><span class="sxs-lookup"><span data-stu-id="da817-107">Needs to be turned on automatically for some situations.</span></span></li><li><span data-ttu-id="da817-108">[] Derleme süresi sonu / / derlenir girişiminde bulunuldu, bir kesme neden olur</span><span class="sxs-lookup"><span data-stu-id="da817-108">[ ] Build-time break // Causes a break if attempted to recompile</span></span></li></ul>|
|<span data-ttu-id="da817-109">Öneri</span><span class="sxs-lookup"><span data-stu-id="da817-109">Suggestion</span></span>|<span data-ttu-id="da817-110">Bir WCF istemcisi aşağıdakilerden birini yaparak bir WCF sunucuya bağlanabilmesi bu soruna geçici çözüm bulabilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="da817-110">You can work around this issue so that a WCF client can connect to a WCF server by doing any of the following:</span></span><ul><li><span data-ttu-id="da817-111">MD5 algoritması kullanmamayı sertifikayı güncelleştirin.</span><span class="sxs-lookup"><span data-stu-id="da817-111">Update the certificate to not use the MD5 algorithm.</span></span> <span data-ttu-id="da817-112">Bu önerilen bir yöntemdir.</span><span class="sxs-lookup"><span data-stu-id="da817-112">This is the recommended solution.</span></span></li><li><span data-ttu-id="da817-113">Bağlama kaynak kodunu dinamik olarak yapılandırılmamışsa, uygulamayı güncelleştirme&#39;TLS 1.1 veya protokolü önceki bir sürümünü kullanmak için s yapılandırma dosyası.</span><span class="sxs-lookup"><span data-stu-id="da817-113">If the binding is not dynamically configured in source code, update the application&#39;s configuration file to use TLS 1.1 or an earlier version of the protocol.</span></span> <span data-ttu-id="da817-114">Bu, bir sertifika ile MD5 karma algoritması kullanmaya devam etmek sağlar.</span><span class="sxs-lookup"><span data-stu-id="da817-114">This allows you to continue to use a certificate with the MD5 hash algorithm.</span></span></li></ul>
<blockquote>
[!WARNING] <span data-ttu-id="da817-115">Bu geçici çözüm önerilmez, bu yana MD5 karma algoritmasını bir sertifikayla güvenli olarak değerlendirilir.</span><span class="sxs-lookup"><span data-stu-id="da817-115">This workaround is not recommended, since a certificate with the MD5 hash algorithm is considered insecure.</span></span></blockquote>
<span data-ttu-id="da817-116">Aşağıdaki yapılandırma dosyası bu yapar:</span><span class="sxs-lookup"><span data-stu-id="da817-116">The following configuration file does this:</span></span><pre><code>&lt;configuration&gt;&#13;&#10;&lt;system.serviceModel&gt;&#13;&#10;&lt;bindings&gt;&#13;&#10;&lt;netTcpBinding&gt;&#13;&#10;&lt;binding&gt;&#13;&#10;&lt;security mode= &quot;None|Transport|Message|TransportWithMessageCredential&quot; &gt;&#13;&#10;&lt;transport clientCredentialType=&quot;None|Windows|Certificate&quot;&#13;&#10;protectionLevel=&quot;None|Sign|EncryptAndSign&quot;&#13;&#10;sslProtocols=&quot;Ssl3|Tls1|Tls11&quot;&gt;&#13;&#10;&lt;/transport&gt;&#13;&#10;&lt;/security&gt;&#13;&#10;&lt;/binding&gt;&#13;&#10;&lt;/netTcpBinding&gt;&#13;&#10;&lt;/bindings&gt;&#13;&#10;&lt;/system.ServiceModel&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre><ul><li><span data-ttu-id="da817-117">Bağlama kaynak kodunu dinamik olarak yapılandırılmışsa, güncelleştirme <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols?displayProperty=nameWithType> TLS 1.1 kullanmak için özelliği (<xref:System.Security.Authentication.SslProtocols.Tls11?displayProperty=nameWithType> veya kaynak kodu protokolünde önceki bir sürümü.</span><span class="sxs-lookup"><span data-stu-id="da817-117">If the binding is dynamically configured in source code, update the <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols?displayProperty=nameWithType> property to use TLS 1.1 (<xref:System.Security.Authentication.SslProtocols.Tls11?displayProperty=nameWithType> or an earlier version of the protocol in the source code.</span></span></li></ul>
<blockquote>
[!WARNING] <span data-ttu-id="da817-118">Bu geçici çözüm önerilmez, bu yana MD5 karma algoritmasını bir sertifikayla güvenli olarak değerlendirilir.</span><span class="sxs-lookup"><span data-stu-id="da817-118">This workaround is not recommended, since a certificate with the MD5 hash algorithm is considered insecure.</span></span></blockquote><span data-ttu-id="da817-119">| | Kapsam | Bilinmeyen | | Sürüm | 4.6 | | Türü | Çalışma zamanı |</span><span class="sxs-lookup"><span data-stu-id="da817-119">| |Scope|Unknown| |Version|4.6| |Type|Runtime|</span></span>
