### <a name="xslt-style-sheet-exception-message-changed"></a>XSLT stil sayfası özel durum iletisi değiştirildi

|   |   |
|---|---|
|Ayrıntılar|.NET Framework 4.5, bir XLST dosyası çok karmaşık olduğunda hata iletisi metindir &quot;stil sayfası çok karmaşık.&quot; Önceki sürümlerde hata iletisi: &quot;XSLT derleme hatası.&quot; Hata iletisindeki metne bağlı olan uygulama kodu artık çalışmaz. Ancak, bu değişikliğin gerçek bir etkisi olmaması gerekir böylece özel durum türleri aynı kalır.|
|Öneri|Yeni ileti beklenen özel durum iletisi bu hata koşulu bağlı olarak herhangi bir uygulama kodu güncelleştirin veya kodu yalnızca özel durum türüne bağlıdır (daha da iyi) güncelleştirme (<xref:System.Xml.Xsl.XsltException?displayProperty=name>), hangi değişmemiştir.|
|Kapsam|Kenar|
|Sürüm|4,5|
|Tür|Çalışma zamanı|
|Etkilenen API'leri|<ul><li><xref:System.Xml.Xsl.XslCompiledTransform.Load(System.String)?displayProperty=nameWithType></li><li><xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Type)?displayProperty=nameWithType></li><li><xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Xml.XmlReader)?displayProperty=nameWithType></li><li><xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Xml.XPath.IXPathNavigable)?displayProperty=nameWithType></li><li><xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Reflection.MethodInfo,System.Byte[],System.Type[])?displayProperty=nameWithType></li><li><xref:System.Xml.Xsl.XslCompiledTransform.Load(System.String,System.Xml.Xsl.XsltSettings,System.Xml.XmlResolver)?displayProperty=nameWithType></li><li><xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Xml.XmlReader,System.Xml.Xsl.XsltSettings,System.Xml.XmlResolver)?displayProperty=nameWithType></li><li><xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Xml.XPath.IXPathNavigable,System.Xml.Xsl.XsltSettings,System.Xml.XmlResolver)?displayProperty=nameWithType></li></ul>|

