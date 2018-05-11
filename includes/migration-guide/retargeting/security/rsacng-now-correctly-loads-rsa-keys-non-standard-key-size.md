### <a name="rsacng-now-correctly-loads-rsa-keys-of-non-standard-key-size"></a><span data-ttu-id="2dd4d-101">RSACng artık doğru şekilde standart anahtar boyutu RSA anahtarları yükler</span><span class="sxs-lookup"><span data-stu-id="2dd4d-101">RSACng now correctly loads RSA keys of non-standard key size</span></span>

|   |   |
|---|---|
|<span data-ttu-id="2dd4d-102">Ayrıntılar</span><span class="sxs-lookup"><span data-stu-id="2dd4d-102">Details</span></span>|<span data-ttu-id="2dd4d-103">RSA sertifikaları için standart olmayan anahtar boyutları müşterilerle 4.6.2 önce .NET Framework sürümleri bu anahtarlar aracılığıyla erişimi sorunu yaşıyor <xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPublicKey(System.Security.Cryptography.X509Certificates.X509Certificate2)?displayProperty=name> ve <xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPrivateKey(System.Security.Cryptography.X509Certificates.X509Certificate2)?displayProperty=name> genişletme yöntemleri.</span><span class="sxs-lookup"><span data-stu-id="2dd4d-103">In .NET Framework versions prior to 4.6.2, customers with non-standard key sizes for RSA certificates are unable to access those keys via the <xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPublicKey(System.Security.Cryptography.X509Certificates.X509Certificate2)?displayProperty=name> and <xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPrivateKey(System.Security.Cryptography.X509Certificates.X509Certificate2)?displayProperty=name> extension methods.</span></span>  <span data-ttu-id="2dd4d-104">A <xref:System.Security.Cryptography.CryptographicException?displayProperty=name> iletiyle &quot;İstenen anahtar boyutu desteklenmiyor&quot; atılır.</span><span class="sxs-lookup"><span data-stu-id="2dd4d-104">A <xref:System.Security.Cryptography.CryptographicException?displayProperty=name> with the message &quot;The requested key size is not supported&quot; is thrown.</span></span> <span data-ttu-id="2dd4d-105">.NET Framework 4.6.2, bu sorun düzeltilmiştir.</span><span class="sxs-lookup"><span data-stu-id="2dd4d-105">In .NET Framework 4.6.2 this issue has been fixed.</span></span> <span data-ttu-id="2dd4d-106">Benzer şekilde, <xref:System.Security.Cryptography.RSA.ImportParameters(System.Security.Cryptography.RSAParameters)> ve <xref:System.Security.Cryptography.RSACng.ImportParameters(System.Security.Cryptography.RSAParameters)> şimdi atma olmadan standart anahtar boyutlarıyla çalışma <xref:System.Security.Cryptography.CryptographicException?displayProperty=name>s.</span><span class="sxs-lookup"><span data-stu-id="2dd4d-106">Similarly, <xref:System.Security.Cryptography.RSA.ImportParameters(System.Security.Cryptography.RSAParameters)> and <xref:System.Security.Cryptography.RSACng.ImportParameters(System.Security.Cryptography.RSAParameters)> now work with non-standard key sizes without throwing <xref:System.Security.Cryptography.CryptographicException?displayProperty=name>s.</span></span>|
|<span data-ttu-id="2dd4d-107">Öneri</span><span class="sxs-lookup"><span data-stu-id="2dd4d-107">Suggestion</span></span>|<span data-ttu-id="2dd4d-108">Herhangi bir özel durum önceki davranışa dayanarak dayanır mantığı işleme ise burada bir <xref:System.Security.Cryptography.CryptographicException?displayProperty=name> standart anahtar boyutları kullanıldığında, durum mantığı kaldırmayı düşünün.</span><span class="sxs-lookup"><span data-stu-id="2dd4d-108">If there is any exception handling logic that relies on the previous behavior where a <xref:System.Security.Cryptography.CryptographicException?displayProperty=name> is thrown when non-standard key sizes are used, consider removing the logic.</span></span>|
|<span data-ttu-id="2dd4d-109">Kapsam</span><span class="sxs-lookup"><span data-stu-id="2dd4d-109">Scope</span></span>|<span data-ttu-id="2dd4d-110">Kenar</span><span class="sxs-lookup"><span data-stu-id="2dd4d-110">Edge</span></span>|
|<span data-ttu-id="2dd4d-111">Sürüm</span><span class="sxs-lookup"><span data-stu-id="2dd4d-111">Version</span></span>|<span data-ttu-id="2dd4d-112">4.6.2</span><span class="sxs-lookup"><span data-stu-id="2dd4d-112">4.6.2</span></span>|
|<span data-ttu-id="2dd4d-113">Tür</span><span class="sxs-lookup"><span data-stu-id="2dd4d-113">Type</span></span>|<span data-ttu-id="2dd4d-114">Yeniden hedefleme</span><span class="sxs-lookup"><span data-stu-id="2dd4d-114">Retargeting</span></span>|
|<span data-ttu-id="2dd4d-115">Etkilenen API'leri</span><span class="sxs-lookup"><span data-stu-id="2dd4d-115">Affected APIs</span></span>|<ul><li><xref:System.Security.Cryptography.RSA.ImportParameters(System.Security.Cryptography.RSAParameters)?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.RSACng.ImportParameters(System.Security.Cryptography.RSAParameters)?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPrivateKey(System.Security.Cryptography.X509Certificates.X509Certificate2)?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPublicKey(System.Security.Cryptography.X509Certificates.X509Certificate2)?displayProperty=nameWithType></li></ul>|
