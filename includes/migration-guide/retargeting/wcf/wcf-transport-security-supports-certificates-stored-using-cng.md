### <a name="wcf-transport-security-supports-certificates-stored-using-cng"></a>WCF aktarım güvenliği kullanarak CNG depolanan sertifikaları destekler.

|   |   |
|---|---|
|Ayrıntılar|.NET Framework 4.6.2'yi hedefleyen uygulamalar ile başlayarak, WCF aktarım güvenliği kullanarak Windows şifreleme kitaplığı (CNG) depolanan sertifikalarını destekler. Bu destek sertifikaları bir üs en fazla 32 bit uzunluğunda bir ortak anahtar ile sınırlıdır. Bir uygulamayı .NET Framework 4.6.2 hedeflediğinde, bu özellik varsayılan olarak açıktır. Önceki .NET Framework sürümlerinde X509 kullanma girişimi sertifikaları bir CSG ile anahtar depolama sağlayıcısı, bir özel durum oluşturur.|
|Öneri|Hedef .NET Framework 4.6.1 ve önceki ancak .NET Framework 4.6.2 üzerinde çalışan uygulamalar, aşağıdaki satırı ekleyerek CNG sertifikalarından desteğini etkinleştirebilirsiniz <code>&lt;runtime&gt;</code> app.config veya web.config dosyasının:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.DisableCngCertificates=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>Bu ayrıca programlı olarak aşağıdaki kod ile yapılabilir:<pre><code class="lang-cs">private const string DisableCngCertificates = @&quot;Switch.System.ServiceModel.DisableCngCertificate&quot;;&#13;&#10;AppContext.SetSwitch(disableCngCertificates, false);&#13;&#10;</code></pre><pre><code class="lang-vb">Const DisableCngCertificates As String = &quot;Switch.System.ServiceModel.DisableCngCertificates&quot;&#13;&#10;AppContext.SetSwitch(disableCngCertificates, False)&#13;&#10;</code></pre>Bu değişiklik nedeniyle, bir özel durum işleme girişimi başarısız bir CNG sertifikası ile güvenli iletişim başlatmak için bağımlı kodunu artık yürütülür, unutmayın.|
|Kapsam|Küçük|
|Sürüm|4.6.2|
|Tür|Yeniden hedefleme|

