### <a name="systemuri-parsing-adheres-to-rfc-3987"></a>System.Uri ayrıştırma için RFC 3987 uyar

|   |   |
|---|---|
|Ayrıntılar|URI ayrıştırma .NET Framework 4.5 birkaç şekilde değişti. Ancak, bu değişiklikleri yalnızca .NET Framework 4.5 hedefleyen kodlarda etkileyeceğini unutmayın. İkili bir hedef .NET Framework 4.0, eski davranışı izlenir. .NET Framework 4. 5 ' URI ayrıştırma değişiklikler şunlardır:<ul><li>URI ayrıştırma normalleştirme ve karakter RFC 3987 yer alan son IRI kurallara uygun denetimi gerçekleştirir.</li><li>Unicode normalleştirme biçimi C yalnızca URI ana bilgisayar bölümü üzerinde gerçekleştirilir.</li><li>Geçersiz mailto: URI'leri bir özel durum neden olur.</li><li>Bir yol parçasının sonundaki sondaki noktalara artık korunur.</li><li><code>file://</code> URI değil kaçış <code>?</code> karakter.</li><li>Unicode denetim karakterlerini <code>U+0080</code> aracılığıyla <code>U+009F</code> desteklenmez.</li><li>Virgül karakterini <code>,</code> veya <code>%2c</code> otomatik olarak atlanmayan değildir.</li></ul>|
|Öneri|Eski .NET Framework 4.0 URI ayrıştırma semantiği (bunlar genellikle olmayan) gerekliyse, .NET Framework 4.0 hedefleyerek kullanılabilir. Bu kullanarak gerçekleştirilebilir bir <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=name> derleme ya da 'proje özelliklerinde' sayfasındaki Visual Studio'nun proje sistem kullanıcı Arabirimi aracılığıyla.|
|Kapsam|Büyük|
|Sürüm|4,5|
|Tür|Yeniden hedefleme|
|Etkilenen API'leri|<ul><li><xref:System.Uri.%23ctor(System.String)?displayProperty=nameWithType></li><li><xref:System.Uri.%23ctor(System.String,System.Boolean)?displayProperty=nameWithType></li><li><xref:System.Uri.%23ctor(System.String,System.UriKind)?displayProperty=nameWithType></li><li><xref:System.Uri.%23ctor(System.Uri,System.String)?displayProperty=nameWithType></li><li><xref:System.Uri.TryCreate(System.String,System.UriKind,System.Uri@)?displayProperty=nameWithType></li><li><xref:System.Uri.TryCreate(System.Uri,System.String,System.Uri@)?displayProperty=nameWithType></li><li><xref:System.Uri.TryCreate(System.Uri,System.Uri,System.Uri@)?displayProperty=nameWithType></li></ul>|

