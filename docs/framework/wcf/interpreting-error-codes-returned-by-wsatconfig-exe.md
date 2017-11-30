---
title: "wsatConfig.exe Tarafından Döndürülen Hata Kodlarını Yorumlama"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ab65f22b-0d69-4c21-9aaf-74acef0ca102
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d8bd70d22b7088a936d3243f050a4ee077d0f5c3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="interpreting-error-codes-returned-by-wsatconfigexe"></a><span data-ttu-id="491e6-102">wsatConfig.exe Tarafından Döndürülen Hata Kodlarını Yorumlama</span><span class="sxs-lookup"><span data-stu-id="491e6-102">Interpreting Error Codes Returned by wsatConfig.exe</span></span>
<span data-ttu-id="491e6-103">Bu konuda tüm hata kodları WS-AtomicTransaction yapılandırma yardımcı programı tarafından (wsatConfig.exe) oluşturulur ve önerilen gerçekleştirilecek eylemleri listeler.</span><span class="sxs-lookup"><span data-stu-id="491e6-103">This topic lists all the error codes generated by the WS-AtomicTransaction Configuration Utility (wsatConfig.exe), and recommended actions to be taken.</span></span>  
  
## <a name="list-of-error-codes"></a><span data-ttu-id="491e6-104">Hata kodları listesi</span><span class="sxs-lookup"><span data-stu-id="491e6-104">List of Error Codes</span></span>  
  
|<span data-ttu-id="491e6-105">Hata Kodu</span><span class="sxs-lookup"><span data-stu-id="491e6-105">Error Code</span></span>|<span data-ttu-id="491e6-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="491e6-106">Description</span></span>|<span data-ttu-id="491e6-107">Gerçekleştirilecek önerilen eylem</span><span class="sxs-lookup"><span data-stu-id="491e6-107">Recommended Action to be Taken</span></span>|  
|----------------|-----------------|------------------------------------|  
|<span data-ttu-id="491e6-108">0</span><span class="sxs-lookup"><span data-stu-id="491e6-108">0</span></span>|<span data-ttu-id="491e6-109">İşlem başarılı oldu</span><span class="sxs-lookup"><span data-stu-id="491e6-109">Operation was successful</span></span>|<span data-ttu-id="491e6-110">Yok.</span><span class="sxs-lookup"><span data-stu-id="491e6-110">None</span></span>|  
|<span data-ttu-id="491e6-111">1.</span><span class="sxs-lookup"><span data-stu-id="491e6-111">1</span></span>|<span data-ttu-id="491e6-112">Beklenmeyen hata</span><span class="sxs-lookup"><span data-stu-id="491e6-112">Unexpected error</span></span>|<span data-ttu-id="491e6-113">Microsoft'a başvurun</span><span class="sxs-lookup"><span data-stu-id="491e6-113">Contact Microsoft</span></span>|  
|<span data-ttu-id="491e6-114">2</span><span class="sxs-lookup"><span data-stu-id="491e6-114">2</span></span>|<span data-ttu-id="491e6-115">MSDTC Güvenlik ayarlarını almak için iletişim kurmaya çalışılırken beklenmeyen bir hata oluştu.</span><span class="sxs-lookup"><span data-stu-id="491e6-115">An unexpected error occurred when trying to contact MSDTC to retrieve its security settings.</span></span>|<span data-ttu-id="491e6-116">MSDTC hizmeti devre dışı ve döndürülen özel durum listelenen tüm sorunları çözün emin olun.</span><span class="sxs-lookup"><span data-stu-id="491e6-116">Ensure that the MSDTC service is not disabled, and address all problems listed in the returned Exception.</span></span>|  
|<span data-ttu-id="491e6-117">3</span><span class="sxs-lookup"><span data-stu-id="491e6-117">3</span></span>|<span data-ttu-id="491e6-118">WsatConfig.exe altında çalıştırıldığı hesabı ağ güvenlik ayarlarını okumak için yeterli izinlere sahip değil.</span><span class="sxs-lookup"><span data-stu-id="491e6-118">The account under which WsatConfig.exe ran did not have sufficient permissions to read the network security settings.</span></span>|<span data-ttu-id="491e6-119">WsatConfig.exe bir yönetici kullanıcı hesabı altında çalıştırın.</span><span class="sxs-lookup"><span data-stu-id="491e6-119">Execute WsatConfig.exe under an Administrator user account.</span></span>|  
|<span data-ttu-id="491e6-120">4</span><span class="sxs-lookup"><span data-stu-id="491e6-120">4</span></span>|<span data-ttu-id="491e6-121">"Ağ DTC erişimi" WS-AT desteğini etkinleştirmek denemeden önce MSDTC için etkinleştirin.</span><span class="sxs-lookup"><span data-stu-id="491e6-121">Enable "Network DTC Access" for MSDTC before trying to enable WS-AT support.</span></span>|<span data-ttu-id="491e6-122">"Ağ DTC erişimi" MSDTC için etkinleştirip yardımcı programı yeniden çalıştırın.</span><span class="sxs-lookup"><span data-stu-id="491e6-122">Enable "Network DTC Access" for MSDTC and re-run the utility.</span></span>|  
|<span data-ttu-id="491e6-123">5</span><span class="sxs-lookup"><span data-stu-id="491e6-123">5</span></span>|<span data-ttu-id="491e6-124">Girilen bağlantı noktası aralığının dışında oluştu.</span><span class="sxs-lookup"><span data-stu-id="491e6-124">The entered port was out of range.</span></span> <span data-ttu-id="491e6-125">Değer 1 ile 65535 aralığında olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="491e6-125">The value must be in the range of 1 to 65535.</span></span>|<span data-ttu-id="491e6-126">Düzeltin`-port:<portNum>`</span><span class="sxs-lookup"><span data-stu-id="491e6-126">Correct the `-port:<portNum>`</span></span><br /><br /> <span data-ttu-id="491e6-127">hata iletisinde belirtildiği gibi komut satırı seçeneği.</span><span class="sxs-lookup"><span data-stu-id="491e6-127">command line option as indicated in the error message.</span></span>|  
|<span data-ttu-id="491e6-128">6</span><span class="sxs-lookup"><span data-stu-id="491e6-128">6</span></span>|<span data-ttu-id="491e6-129">Geçersiz uç nokta sertifikası komut satırında belirtildi.</span><span class="sxs-lookup"><span data-stu-id="491e6-129">An invalid endpoint certificate was specified on the command line.</span></span>  <span data-ttu-id="491e6-130">Sertifika bulunamadı veya doğrulamayı geçemedi.</span><span class="sxs-lookup"><span data-stu-id="491e6-130">The certificate could not be found, or it did not pass verification.</span></span>|<span data-ttu-id="491e6-131">Düzeltmek `-endpointCert` komut satırı seçeneği.</span><span class="sxs-lookup"><span data-stu-id="491e6-131">Correct the `-endpointCert` command line option.</span></span> <span data-ttu-id="491e6-132">Sertifika bir özel anahtara sahip, ClientAuthentication ve ServerAuthentication için kullanılmak üzere tasarlanmıştır, LocalMachine\MY sertifika deposunda yüklü ve tam güvenilir olduğundan emin olun.</span><span class="sxs-lookup"><span data-stu-id="491e6-132">Ensure that the certificate has a private key, is intended to be used for both ClientAuthentication and ServerAuthentication, is installed in the LocalMachine\MY certificate store, and is fully trusted.</span></span>|  
|<span data-ttu-id="491e6-133">7</span><span class="sxs-lookup"><span data-stu-id="491e6-133">7</span></span>|<span data-ttu-id="491e6-134">Geçersiz hesap sertifikası komut satırında belirtildi.</span><span class="sxs-lookup"><span data-stu-id="491e6-134">An invalid accounts certificate was specified on the command line.</span></span>|<span data-ttu-id="491e6-135">Düzeltmek `-accountsCerts` komut satırı seçeneği.</span><span class="sxs-lookup"><span data-stu-id="491e6-135">Correct the `-accountsCerts` command line option.</span></span> <span data-ttu-id="491e6-136">Belirtilen sertifika yanlış belirtildi ya da bulunamadı.</span><span class="sxs-lookup"><span data-stu-id="491e6-136">The certificate specified was either improperly specified or it could not be found.</span></span>|  
|<span data-ttu-id="491e6-137">8</span><span class="sxs-lookup"><span data-stu-id="491e6-137">8</span></span>|<span data-ttu-id="491e6-138">Varsayılan zaman aşımı 1-3600 saniye aralığın dışında belirtildi.</span><span class="sxs-lookup"><span data-stu-id="491e6-138">A default timeout was specified outside the range of 1 to 3600 seconds.</span></span>|<span data-ttu-id="491e6-139">Belirtildiği gibi bir doğru varsayılan zaman aşımı değeri girin.</span><span class="sxs-lookup"><span data-stu-id="491e6-139">Enter a correct default timeout value as indicated.</span></span>|  
|<span data-ttu-id="491e6-140">10</span><span class="sxs-lookup"><span data-stu-id="491e6-140">10</span></span>|<span data-ttu-id="491e6-141">Kayıt defterine erişim çalışılırken beklenmeyen bir hata oluştu.</span><span class="sxs-lookup"><span data-stu-id="491e6-141">An unexpected error occurred while trying to access the registry.</span></span>|<span data-ttu-id="491e6-142">Hata iletisi ve tıklatılabilir öğeleri için hata kodunu kontrol edin</span><span class="sxs-lookup"><span data-stu-id="491e6-142">Check the error message and error code for actionable items</span></span>|  
|<span data-ttu-id="491e6-143">11</span><span class="sxs-lookup"><span data-stu-id="491e6-143">11</span></span>|<span data-ttu-id="491e6-144">Kayıt defterine yazılamıyor.</span><span class="sxs-lookup"><span data-stu-id="491e6-144">Cannot write to the registry.</span></span>|<span data-ttu-id="491e6-145">Hata iletisinde listelenen anahtar kayıt defteri erişimi WsatConfig.exe altında yürütüldüğü hesabından destekleme kapasitesine sahip olduğundan emin olun.</span><span class="sxs-lookup"><span data-stu-id="491e6-145">Ensure that the key listed in the error message is capable of supporting registry access from the account WsatConfig.exe was executed under.</span></span>|  
|<span data-ttu-id="491e6-146">12</span><span class="sxs-lookup"><span data-stu-id="491e6-146">12</span></span>|<span data-ttu-id="491e6-147">Sertifika deposuna erişim çalışılırken beklenmeyen bir hata oluştu.</span><span class="sxs-lookup"><span data-stu-id="491e6-147">An unexpected error occurred while trying to access the certificate store.</span></span>|<span data-ttu-id="491e6-148">İçin uygun sistem hatası eşlemek için döndürülen hata kodu kullanın.</span><span class="sxs-lookup"><span data-stu-id="491e6-148">Use the error code returned to map to the appropriate system error.</span></span>|  
|<span data-ttu-id="491e6-149">13</span><span class="sxs-lookup"><span data-stu-id="491e6-149">13</span></span>|<span data-ttu-id="491e6-150">Http.sys yapılandırması başarısız oldu.</span><span class="sxs-lookup"><span data-stu-id="491e6-150">Configuration of http.sys failed.</span></span> <span data-ttu-id="491e6-151">Yeni bir HTTPS bağlantı noktası ayırma MSDTC için oluşturulamıyor.</span><span class="sxs-lookup"><span data-stu-id="491e6-151">Cannot create a new HTTPS port reservation for MSDTC.</span></span>|<span data-ttu-id="491e6-152">İçin uygun sistem hatası eşlemek için döndürülen hata kodu kullanın.</span><span class="sxs-lookup"><span data-stu-id="491e6-152">Use the error code returned to map to the appropriate system error.</span></span>|  
|<span data-ttu-id="491e6-153">14</span><span class="sxs-lookup"><span data-stu-id="491e6-153">14</span></span>|<span data-ttu-id="491e6-154">Http.sys yapılandırması başarısız oldu.</span><span class="sxs-lookup"><span data-stu-id="491e6-154">Configuration of http.sys failed.</span></span> <span data-ttu-id="491e6-155">MSDTC için önceki HTTPS bağlantı noktası ayırma kaldıramazsınız.</span><span class="sxs-lookup"><span data-stu-id="491e6-155">Cannot remove previous HTTPS port reservation for MSDTC.</span></span>|<span data-ttu-id="491e6-156">İçin uygun sistem hatası eşlemek için döndürülen hata kodu kullanın.</span><span class="sxs-lookup"><span data-stu-id="491e6-156">Use the error code returned to map to the appropriate system error.</span></span>|  
|<span data-ttu-id="491e6-157">15</span><span class="sxs-lookup"><span data-stu-id="491e6-157">15</span></span>|<span data-ttu-id="491e6-158">Http.sys yapılandırması başarısız oldu.</span><span class="sxs-lookup"><span data-stu-id="491e6-158">Configuration of http.sys failed.</span></span> <span data-ttu-id="491e6-159">Belirtilen bağlantı noktası için bir önceki HTTPS bağlantı noktası ayırma zaten var.</span><span class="sxs-lookup"><span data-stu-id="491e6-159">A previous HTTPS port reservation already exists for the specified port.</span></span>|<span data-ttu-id="491e6-160">Başka bir uygulama zaten belirli bağlantı noktası sahipliğini sürdü.</span><span class="sxs-lookup"><span data-stu-id="491e6-160">Another application has already taken ownership of the specific port.</span></span> <span data-ttu-id="491e6-161">Farklı bir bağlantı noktasına değiştirin veya kaldırın veya geçerli uygulama yeniden yapılandırın.</span><span class="sxs-lookup"><span data-stu-id="491e6-161">Change to a different port or uninstall or reconfigure the current application.</span></span>|  
|<span data-ttu-id="491e6-162">16</span><span class="sxs-lookup"><span data-stu-id="491e6-162">16</span></span>|<span data-ttu-id="491e6-163">Http.sys yapılandırması başarısız oldu.</span><span class="sxs-lookup"><span data-stu-id="491e6-163">Configuration of http.sys failed.</span></span> <span data-ttu-id="491e6-164">Belirtilen sertifika bağlantı noktasına bağlanılamıyor.</span><span class="sxs-lookup"><span data-stu-id="491e6-164">Cannot bind the specified certificate to the port.</span></span>|<span data-ttu-id="491e6-165">Hata iletisinde döndürülen hata kodu için uygun sistem hatası eşlemek için kullanın</span><span class="sxs-lookup"><span data-stu-id="491e6-165">Use the error code returned in the error message to map to the appropriate system error</span></span>|  
|<span data-ttu-id="491e6-166">17</span><span class="sxs-lookup"><span data-stu-id="491e6-166">17</span></span>|<span data-ttu-id="491e6-167">Http.sys yapılandırması başarısız oldu.</span><span class="sxs-lookup"><span data-stu-id="491e6-167">Configuration of http.sys failed.</span></span> <span data-ttu-id="491e6-168">Önceki bağlantı noktasından SSL sertifikası ile olan bağlantı kesilemiyor.</span><span class="sxs-lookup"><span data-stu-id="491e6-168">Cannot unbind the SSL certificate from the previous port.</span></span>|<span data-ttu-id="491e6-169">Hata iletisinde döndürülen hata kodu için uygun sistem hatası eşlemek için kullanın.</span><span class="sxs-lookup"><span data-stu-id="491e6-169">Use the error code returned in the error message to map to the appropriate system error.</span></span> <span data-ttu-id="491e6-170">Gerekirse, httpcfg.exe veya netsh.exe hatalı bağlantı noktası ayırmaları kaldırmak için kullanın.</span><span class="sxs-lookup"><span data-stu-id="491e6-170">If necessary, use httpcfg.exe or netsh.exe to remove the erroneous port reservations.</span></span>|  
|<span data-ttu-id="491e6-171">18</span><span class="sxs-lookup"><span data-stu-id="491e6-171">18</span></span>|<span data-ttu-id="491e6-172">Http.sys yapılandırması başarısız oldu.</span><span class="sxs-lookup"><span data-stu-id="491e6-172">Configuration of http.sys failed.</span></span> <span data-ttu-id="491e6-173">Belirtilen sertifika çünkü bağlantı noktasına bağlanılamıyor önceki bir SSL bağlaması zaten mevcut.</span><span class="sxs-lookup"><span data-stu-id="491e6-173">Cannot bind the specified certificate to the port because a previous SSL binding already exists.</span></span>|<span data-ttu-id="491e6-174">Başka bir uygulama zaten belirli bağlantı noktası sahipliğini sürdü.</span><span class="sxs-lookup"><span data-stu-id="491e6-174">Another application has already taken ownership of the specific port.</span></span> <span data-ttu-id="491e6-175">Farklı bir bağlantı noktasına değiştirin veya kaldırın veya geçerli uygulama yeniden yapılandırın.</span><span class="sxs-lookup"><span data-stu-id="491e6-175">Change to a different port or uninstall or reconfigure the current application.</span></span>|  
|<span data-ttu-id="491e6-176">19</span><span class="sxs-lookup"><span data-stu-id="491e6-176">19</span></span>|<span data-ttu-id="491e6-177">MSDTC yeniden başlatma başarısız oldu</span><span class="sxs-lookup"><span data-stu-id="491e6-177">Restarting MSDTC failed</span></span>|<span data-ttu-id="491e6-178">Gerekirse MSDTC el ile yeniden başlatın.</span><span class="sxs-lookup"><span data-stu-id="491e6-178">Manually restart MSDTC if necessary.</span></span> <span data-ttu-id="491e6-179">Sorun devam ederse, Microsoft ile iletişime geçin.</span><span class="sxs-lookup"><span data-stu-id="491e6-179">If the problem persists, contact Microsoft.</span></span>|  
|<span data-ttu-id="491e6-180">20</span><span class="sxs-lookup"><span data-stu-id="491e6-180">20</span></span>|[!INCLUDE[vstecwinfx](../../../includes/vstecwinfx-md.md)]<span data-ttu-id="491e6-181">uzak makinede yüklü değil veya düzgün şekilde yüklenmemiş.</span><span class="sxs-lookup"><span data-stu-id="491e6-181"> is not installed on the remote machine, or is not installed correctly.</span></span>|<span data-ttu-id="491e6-182">Yükleme [!INCLUDE[vstecwinfx](../../../includes/vstecwinfx-md.md)] makinedeki.</span><span class="sxs-lookup"><span data-stu-id="491e6-182">Install [!INCLUDE[vstecwinfx](../../../includes/vstecwinfx-md.md)] on the machine.</span></span>|  
|<span data-ttu-id="491e6-183">21</span><span class="sxs-lookup"><span data-stu-id="491e6-183">21</span></span>|<span data-ttu-id="491e6-184">Uzaktan yapılandırma işlemi zaman aşımına uğramadan nedeniyle başarısız oldu.</span><span class="sxs-lookup"><span data-stu-id="491e6-184">Remote configuration failed due to the operation timing out.</span></span>|<span data-ttu-id="491e6-185">WS-AT uzak makinede yapılandırmak için çağrı 90 saniyeden daha uzun sürer.</span><span class="sxs-lookup"><span data-stu-id="491e6-185">The call to configure WS-AT on the remote machine should take longer than 90 seconds.</span></span>|  
|<span data-ttu-id="491e6-186">22</span><span class="sxs-lookup"><span data-stu-id="491e6-186">22</span></span>|[!INCLUDE[vstecwinfx](../../../includes/vstecwinfx-md.md)]<span data-ttu-id="491e6-187">uzak makinede yüklü değil veya düzgün şekilde yüklenmemiş.</span><span class="sxs-lookup"><span data-stu-id="491e6-187"> is not installed on the remote machine, or is not installed correctly.</span></span>|<span data-ttu-id="491e6-188">Yükleme [!INCLUDE[vstecwinfx](../../../includes/vstecwinfx-md.md)] makinedeki.</span><span class="sxs-lookup"><span data-stu-id="491e6-188">Install [!INCLUDE[vstecwinfx](../../../includes/vstecwinfx-md.md)] on the machine.</span></span>|  
|<span data-ttu-id="491e6-189">23</span><span class="sxs-lookup"><span data-stu-id="491e6-189">23</span></span>|<span data-ttu-id="491e6-190">Uzaktan yapılandırma uzak makinede bir özel durum nedeniyle başarısız oldu.</span><span class="sxs-lookup"><span data-stu-id="491e6-190">Remote configuration failed due to an exception on the remote machine.</span></span>|<span data-ttu-id="491e6-191">Kullanılabilir öğeleri için hata iletisini kontrol edin</span><span class="sxs-lookup"><span data-stu-id="491e6-191">Check the error message for actionable items</span></span>|  
|<span data-ttu-id="491e6-192">26</span><span class="sxs-lookup"><span data-stu-id="491e6-192">26</span></span>|<span data-ttu-id="491e6-193">WsatConfig.exe için geçersiz bağımsız değişken geçirildi.</span><span class="sxs-lookup"><span data-stu-id="491e6-193">An invalid argument was passed to WsatConfig.exe.</span></span>|<span data-ttu-id="491e6-194">Komut satırı hataları denetleyin.</span><span class="sxs-lookup"><span data-stu-id="491e6-194">Check the command line for errors.</span></span>|  
|<span data-ttu-id="491e6-195">27</span><span class="sxs-lookup"><span data-stu-id="491e6-195">27</span></span>|<span data-ttu-id="491e6-196">`-accounts` Komut satırı seçeneği geçersiz.</span><span class="sxs-lookup"><span data-stu-id="491e6-196">The `-accounts` command line option was invalid.</span></span>|<span data-ttu-id="491e6-197">Düzeltmek`accounts` doğru bir kullanıcı hesabı belirtmek için komut satırı seçeneği.</span><span class="sxs-lookup"><span data-stu-id="491e6-197">Correct the -`accounts` command line option to correctly specify a user account.</span></span>|  
|<span data-ttu-id="491e6-198">28</span><span class="sxs-lookup"><span data-stu-id="491e6-198">28</span></span>|<span data-ttu-id="491e6-199">`-network` Komut satırı seçeneği geçersiz.</span><span class="sxs-lookup"><span data-stu-id="491e6-199">The `-network` command line option was invalid.</span></span>|<span data-ttu-id="491e6-200">Düzeltmek `-network` doğru "etkinleştir" belirtmek için komut satırı seçeneği veya "devre dışı bırak".</span><span class="sxs-lookup"><span data-stu-id="491e6-200">Correct the `-network` command line option to correctly specify "enable" or "disable".</span></span>|  
|<span data-ttu-id="491e6-201">29</span><span class="sxs-lookup"><span data-stu-id="491e6-201">29</span></span>|<span data-ttu-id="491e6-202">`-maxTimeout` Komut satırı seçeneği geçersiz.</span><span class="sxs-lookup"><span data-stu-id="491e6-202">The `-maxTimeout` command line option was invalid.</span></span>|<span data-ttu-id="491e6-203">Düzeltmek `-maxTimeout` belirtildiği gibi komut satırı seçeneği.</span><span class="sxs-lookup"><span data-stu-id="491e6-203">Correct the `-maxTimeout` command line option as indicated.</span></span>|  
|<span data-ttu-id="491e6-204">30</span><span class="sxs-lookup"><span data-stu-id="491e6-204">30</span></span>|<span data-ttu-id="491e6-205">`-timeout` Komut satırı seçeneği geçersiz.</span><span class="sxs-lookup"><span data-stu-id="491e6-205">The `-timeout` command line option was invalid.</span></span>|<span data-ttu-id="491e6-206">Düzeltmek `-timeout` belirtildiği gibi komut satırı seçeneği.</span><span class="sxs-lookup"><span data-stu-id="491e6-206">Correct the `-timeout` command line option as indicated.</span></span>|  
|<span data-ttu-id="491e6-207">31</span><span class="sxs-lookup"><span data-stu-id="491e6-207">31</span></span>|<span data-ttu-id="491e6-208">`-traceLevel` Komut satırı seçeneği geçersiz.</span><span class="sxs-lookup"><span data-stu-id="491e6-208">The `-traceLevel` command line option was invalid.</span></span>|<span data-ttu-id="491e6-209">Düzeltmek `-traceLevel` aşağıdakilere arasında geçerli bir değer belirtmek için komut satırı seçeneği</span><span class="sxs-lookup"><span data-stu-id="491e6-209">Correct the `-traceLevel` command line option to specify a valid value from the followings,</span></span><br /><br /> <span data-ttu-id="491e6-210">-Kapalı</span><span class="sxs-lookup"><span data-stu-id="491e6-210">-   Off</span></span><br /><span data-ttu-id="491e6-211">-Hata</span><span class="sxs-lookup"><span data-stu-id="491e6-211">-   Error</span></span><br /><span data-ttu-id="491e6-212">-Kritik</span><span class="sxs-lookup"><span data-stu-id="491e6-212">-   Critical</span></span><br /><span data-ttu-id="491e6-213">-Uyarı</span><span class="sxs-lookup"><span data-stu-id="491e6-213">-   Warning</span></span><br /><span data-ttu-id="491e6-214">-Bilgileri</span><span class="sxs-lookup"><span data-stu-id="491e6-214">-   Information</span></span><br /><span data-ttu-id="491e6-215">-Verbose</span><span class="sxs-lookup"><span data-stu-id="491e6-215">-   Verbose</span></span><br /><span data-ttu-id="491e6-216">-Tüm</span><span class="sxs-lookup"><span data-stu-id="491e6-216">-   All</span></span>|  
|<span data-ttu-id="491e6-217">32</span><span class="sxs-lookup"><span data-stu-id="491e6-217">32</span></span>|<span data-ttu-id="491e6-218">`-traceActivity` Komut satırı seçeneği geçersiz.</span><span class="sxs-lookup"><span data-stu-id="491e6-218">The `-traceActivity` command line option was invalid.</span></span>|<span data-ttu-id="491e6-219">Düzeltmek `-traceActivity` "etkinleştir" veya "devre dışı bırak" belirterek komut satırı seçeneği.</span><span class="sxs-lookup"><span data-stu-id="491e6-219">Correct the `-traceActivity` command line option by specifying either "enable" or "disable".</span></span>|  
|<span data-ttu-id="491e6-220">33</span><span class="sxs-lookup"><span data-stu-id="491e6-220">33</span></span>|<span data-ttu-id="491e6-221">`-traceProp` Komut satırı seçeneği geçersiz.</span><span class="sxs-lookup"><span data-stu-id="491e6-221">The `-traceProp` command line option was invalid.</span></span>|<span data-ttu-id="491e6-222">Düzeltmek `-traceProp` "etkinleştir" veya "devre dışı bırak" belirterek komut satırı seçeneği.</span><span class="sxs-lookup"><span data-stu-id="491e6-222">Correct the `-traceProp` command line option by specifying either "enable" or "disable".</span></span>|  
|<span data-ttu-id="491e6-223">34</span><span class="sxs-lookup"><span data-stu-id="491e6-223">34</span></span>|<span data-ttu-id="491e6-224">`-tracePII` Komut satırı seçeneği geçersiz.</span><span class="sxs-lookup"><span data-stu-id="491e6-224">The `-tracePII` command line option was invalid.</span></span>|<span data-ttu-id="491e6-225">Düzeltmek `-tracePII` "etkinleştir" veya "devre dışı bırak" belirterek komut satırı seçeneği.</span><span class="sxs-lookup"><span data-stu-id="491e6-225">Correct the `-tracePII` command line option by specifying either "enable" or "disable".</span></span>|  
|<span data-ttu-id="491e6-226">37</span><span class="sxs-lookup"><span data-stu-id="491e6-226">37</span></span>|<span data-ttu-id="491e6-227">WsatConfig.exe tam makine sertifikası belirlemek mümkün değildi.</span><span class="sxs-lookup"><span data-stu-id="491e6-227">WsatConfig.exe was not able to determine the exact machine certificate.</span></span> <span data-ttu-id="491e6-228">Birden fazla aday olduğunda ya da hiçbiri mevcut olduğunda gerçekleşebilir.</span><span class="sxs-lookup"><span data-stu-id="491e6-228">This might happen when there is more than one candidate, or when none exists.</span></span>|<span data-ttu-id="491e6-229">Bir sertifika parmak izi veya doğru şekilde yapılandırmak için tam sertifikayı belirlemek için Issuer\SubjectName çifti belirtin.</span><span class="sxs-lookup"><span data-stu-id="491e6-229">Specify a certificate thumbprint or Issuer\SubjectName pair to correctly identify the exact certificate to configure.</span></span>|  
|<span data-ttu-id="491e6-230">38</span><span class="sxs-lookup"><span data-stu-id="491e6-230">38</span></span>|<span data-ttu-id="491e6-231">İşlemin veya kullanıcı güvenlik duvarı yapılandırmasını değiştirmek için yeterli izinlere sahip değil.</span><span class="sxs-lookup"><span data-stu-id="491e6-231">The process or user does not have sufficient permissions to change the firewall configuration.</span></span>|<span data-ttu-id="491e6-232">WsatConfig.exe bir yönetici kullanıcı hesabı altında çalıştırın.</span><span class="sxs-lookup"><span data-stu-id="491e6-232">Execute WsatConfig.exe under an Administrator user account.</span></span>|  
|<span data-ttu-id="491e6-233">39</span><span class="sxs-lookup"><span data-stu-id="491e6-233">39</span></span>|<span data-ttu-id="491e6-234">WsatConfig.exe güvenlik duvarı yapılandırması güncelleştirilirken bir hatayla karşılaştı.</span><span class="sxs-lookup"><span data-stu-id="491e6-234">WsatConfig.exe encountered an error while updating the firewall configuration.</span></span>|<span data-ttu-id="491e6-235">Kullanılabilir öğeleri için hata iletisini kontrol edin.</span><span class="sxs-lookup"><span data-stu-id="491e6-235">Check the error message for actionable items.</span></span>|  
|<span data-ttu-id="491e6-236">40</span><span class="sxs-lookup"><span data-stu-id="491e6-236">40</span></span>|<span data-ttu-id="491e6-237">WsatConfig.exe sertifikanın özel anahtarı dosyasına MSDTC okuma erişimi verin mümkün değil</span><span class="sxs-lookup"><span data-stu-id="491e6-237">WsatConfig.exe is not able to give MSDTC Read access to the certificate's private key file</span></span>|<span data-ttu-id="491e6-238">WsatConfig.exe bir yönetici kullanıcı hesabı altında çalıştırın.</span><span class="sxs-lookup"><span data-stu-id="491e6-238">Execute WsatConfig.exe under an Administrator user account.</span></span>|  
|<span data-ttu-id="491e6-239">41</span><span class="sxs-lookup"><span data-stu-id="491e6-239">41</span></span>|<span data-ttu-id="491e6-240">Yok ya da yüklemesi [!INCLUDE[vstecwinfx](../../../includes/vstecwinfx-md.md)] bulunamadı veya bulunan sürüm aracı yapılandırmayı özellikli nedir eşleşmiyor.</span><span class="sxs-lookup"><span data-stu-id="491e6-240">Either no installation of [!INCLUDE[vstecwinfx](../../../includes/vstecwinfx-md.md)] could be found, or the version found does not match what the tool is capable of configuring.</span></span>|<span data-ttu-id="491e6-241">Olun [!INCLUDE[vstecwinfx](../../../includes/vstecwinfx-md.md)] doğru şekilde yüklendiğinden ve yalnızca kullanılır, bu sürümü ile gelen WsatConfig.exe aracı [!INCLUDE[vstecwinfx](../../../includes/vstecwinfx-md.md)] WS-AT yapılandırmak için.</span><span class="sxs-lookup"><span data-stu-id="491e6-241">Ensure [!INCLUDE[vstecwinfx](../../../includes/vstecwinfx-md.md)] is correctly installed and only use the WsatConfig.exe tool that came with that version of [!INCLUDE[vstecwinfx](../../../includes/vstecwinfx-md.md)] to configure WS-AT.</span></span>|  
|<span data-ttu-id="491e6-242">42</span><span class="sxs-lookup"><span data-stu-id="491e6-242">42</span></span>|<span data-ttu-id="491e6-243">Bağımsız değişken, komut satırında birden çok kez belirtildi.</span><span class="sxs-lookup"><span data-stu-id="491e6-243">An argument was specified more than once on the command line.</span></span>|<span data-ttu-id="491e6-244">Yalnızca her bir bağımsız değişkeni bir kez WsatConfig.exe yürütülürken belirtin.</span><span class="sxs-lookup"><span data-stu-id="491e6-244">Only specify each argument once when executing WsatConfig.exe.</span></span>|  
|<span data-ttu-id="491e6-245">43</span><span class="sxs-lookup"><span data-stu-id="491e6-245">43</span></span>|<span data-ttu-id="491e6-246">WS-AT etkin değilse WsatConfig.exe WS-AT ayarları güncelleştirilemiyor.</span><span class="sxs-lookup"><span data-stu-id="491e6-246">WsatConfig.exe cannot update WS-AT settings if WS-AT is not enabled.</span></span>|<span data-ttu-id="491e6-247">Belirtin `-network:enable` ek komut satırı bağımsız değişken olarak.</span><span class="sxs-lookup"><span data-stu-id="491e6-247">Specify `-network:enable` as an additional command line argument.</span></span>|  
|<span data-ttu-id="491e6-248">44</span><span class="sxs-lookup"><span data-stu-id="491e6-248">44</span></span>|<span data-ttu-id="491e6-249">Gerekli düzeltme eksik ve WS-AT düzeltme yüklenene kadar yapılandırılamaz.</span><span class="sxs-lookup"><span data-stu-id="491e6-249">A required hotfix is missing and WS-AT cannot be configured until the hotfix is installed.</span></span>|<span data-ttu-id="491e6-250">Bkz: [!INCLUDE[vstecwinfx](../../../includes/vstecwinfx-md.md)] gerekli düzeltme yükleme yönergeleri için sürüm notları.</span><span class="sxs-lookup"><span data-stu-id="491e6-250">See the [!INCLUDE[vstecwinfx](../../../includes/vstecwinfx-md.md)] release notes for instructions on installing the required hotfix.</span></span>|  
|<span data-ttu-id="491e6-251">45</span><span class="sxs-lookup"><span data-stu-id="491e6-251">45</span></span>|<span data-ttu-id="491e6-252">`-virtualServer` Komut satırı seçeneği geçersiz.</span><span class="sxs-lookup"><span data-stu-id="491e6-252">The `-virtualServer` command line option was invalid.</span></span>|<span data-ttu-id="491e6-253">Düzeltmek `-virtualServer` küme kaynağı yapılandırmak üzere ağ adını belirterek komut satırı seçeneği.</span><span class="sxs-lookup"><span data-stu-id="491e6-253">Correct the `-virtualServer` command line option by specifying the network name of the cluster resource in which to configure.</span></span>|  
|<span data-ttu-id="491e6-254">46</span><span class="sxs-lookup"><span data-stu-id="491e6-254">46</span></span>|<span data-ttu-id="491e6-255">ETW izleme oturumunu Başlat çalışılırken beklenmeyen bir hata oluştu</span><span class="sxs-lookup"><span data-stu-id="491e6-255">An unexpected error occurred when trying to start the ETW trace session</span></span>|<span data-ttu-id="491e6-256">İçin uygun sistem hatası eşlemek için döndürülen hata kodu kullanın.</span><span class="sxs-lookup"><span data-stu-id="491e6-256">Use the error code returned to map to the appropriate system error.</span></span>|  
|<span data-ttu-id="491e6-257">47</span><span class="sxs-lookup"><span data-stu-id="491e6-257">47</span></span>|<span data-ttu-id="491e6-258">İşlemin veya kullanıcı ETW izleme oturumunu etkinleştirmek için yeterli izinlere sahip değil.</span><span class="sxs-lookup"><span data-stu-id="491e6-258">The process or user does not have sufficient permissions to enable the ETW trace session.</span></span>|<span data-ttu-id="491e6-259">WsatConfig.exe bir yönetici kullanıcı hesabı altında çalıştırın.</span><span class="sxs-lookup"><span data-stu-id="491e6-259">Execute WsatConfig.exe under an Administrator user account.</span></span>|  
|<span data-ttu-id="491e6-260">48</span><span class="sxs-lookup"><span data-stu-id="491e6-260">48</span></span>|<span data-ttu-id="491e6-261">ETW izleme oturumunu başlatılmaya çalışılırken beklenmeyen bir hata oluştu.</span><span class="sxs-lookup"><span data-stu-id="491e6-261">An unexpected error occurred while trying to start the ETW trace session.</span></span>|<span data-ttu-id="491e6-262">Microsoft ile iletişime geçin.</span><span class="sxs-lookup"><span data-stu-id="491e6-262">Contact Microsoft.</span></span>|  
|<span data-ttu-id="491e6-263">49</span><span class="sxs-lookup"><span data-stu-id="491e6-263">49</span></span>|<span data-ttu-id="491e6-264">% Systemdrive % üzerinde yeterli alan nedeniyle yeni bir günlük dosyası oluşturulamıyor</span><span class="sxs-lookup"><span data-stu-id="491e6-264">Cannot create a new log file due to insufficient space on the %systemdrive%</span></span>|<span data-ttu-id="491e6-265">% SYSTEMDRIVE % günlük dosyası için yeterli alana sahip olduğundan emin olun.</span><span class="sxs-lookup"><span data-stu-id="491e6-265">Ensure that your %systemdrive% has adequate space for the log file.</span></span>|  
|<span data-ttu-id="491e6-266">51</span><span class="sxs-lookup"><span data-stu-id="491e6-266">51</span></span>|<span data-ttu-id="491e6-267">ETW izleme oturumunu başlatılmaya çalışılırken beklenmeyen bir hata oluştu.</span><span class="sxs-lookup"><span data-stu-id="491e6-267">An unexpected error occurred while trying to start the ETW trace session.</span></span>|<span data-ttu-id="491e6-268">Microsoft ile iletişime geçin.</span><span class="sxs-lookup"><span data-stu-id="491e6-268">Contact Microsoft.</span></span>|  
|<span data-ttu-id="491e6-269">52</span><span class="sxs-lookup"><span data-stu-id="491e6-269">52</span></span>|<span data-ttu-id="491e6-270">ETW izleme oturumunu başlatılmaya çalışılırken beklenmeyen bir hata oluştu.</span><span class="sxs-lookup"><span data-stu-id="491e6-270">An unexpected error occurred while trying to start the ETW trace session.</span></span>|<span data-ttu-id="491e6-271">Microsoft ile iletişime geçin.</span><span class="sxs-lookup"><span data-stu-id="491e6-271">Contact Microsoft.</span></span>|  
|<span data-ttu-id="491e6-272">53</span><span class="sxs-lookup"><span data-stu-id="491e6-272">53</span></span>|<span data-ttu-id="491e6-273">Önceki ETW oturum günlük dosyasının yedekleme başarısız oldu.</span><span class="sxs-lookup"><span data-stu-id="491e6-273">Backup of the previous ETW session log file was unsuccessful.</span></span>|<span data-ttu-id="491e6-274">% SYSTEMDRIVE % (varsa) günlük dosyası ve bir önceki günlük dosyası yedekleme için yeterli alana sahip olduğundan emin olun.</span><span class="sxs-lookup"><span data-stu-id="491e6-274">Ensure that your %systemdrive% has adequate space for the log file and the backup of the previous log file (if any).</span></span> <span data-ttu-id="491e6-275">Önceki günlük dosyası, gerekirse el ile kaldırın.</span><span class="sxs-lookup"><span data-stu-id="491e6-275">Remove the previous log file manually if necessary.</span></span>|  
|<span data-ttu-id="491e6-276">55</span><span class="sxs-lookup"><span data-stu-id="491e6-276">55</span></span>|<span data-ttu-id="491e6-277">ETW izleme oturumunu başlatılmaya çalışılırken beklenmeyen bir hata oluştu.</span><span class="sxs-lookup"><span data-stu-id="491e6-277">An unexpected error occurred while trying to start the ETW trace session.</span></span>|<span data-ttu-id="491e6-278">Microsoft ile iletişime geçin.</span><span class="sxs-lookup"><span data-stu-id="491e6-278">Contact Microsoft.</span></span>|  
|<span data-ttu-id="491e6-279">56</span><span class="sxs-lookup"><span data-stu-id="491e6-279">56</span></span>|<span data-ttu-id="491e6-280">ETW izleme oturumunu başlatılmaya çalışılırken beklenmeyen bir hata oluştu.</span><span class="sxs-lookup"><span data-stu-id="491e6-280">An unexpected error occurred while trying to start the ETW trace session.</span></span>|<span data-ttu-id="491e6-281">Microsoft ile iletişime geçin.</span><span class="sxs-lookup"><span data-stu-id="491e6-281">Contact Microsoft.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="491e6-282">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="491e6-282">See Also</span></span>  
 [<span data-ttu-id="491e6-283">WS-AtomicTransaction yapılandırma yardımcı programı (wsatConfig.exe)</span><span class="sxs-lookup"><span data-stu-id="491e6-283">WS-AtomicTransaction Configuration Utility (wsatConfig.exe)</span></span>](../../../docs/framework/wcf/ws-atomictransaction-configuration-utility-wsatconfig-exe.md)