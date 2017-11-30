---
title: "SqlClient akış desteği"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c449365b-470b-4edb-9d61-8353149f5531
caps.latest.revision: "14"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 85999a6aa15b04ffa2751d7312f71aaab1582ea3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="sqlclient-streaming-support"></a><span data-ttu-id="f5cde-102">SqlClient akış desteği</span><span class="sxs-lookup"><span data-stu-id="f5cde-102">SqlClient Streaming Support</span></span>
<span data-ttu-id="f5cde-103">Akış desteği arasında [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] ve bir uygulama (yeni [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)]) (belgeler, görüntüler ve medya dosyaları) sunucuda yapılandırılmamış verileri destekler.</span><span class="sxs-lookup"><span data-stu-id="f5cde-103">Streaming support between [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] and an application (new in [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)]) supports unstructured data on the server (documents, images, and media files).</span></span> <span data-ttu-id="f5cde-104">A [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] veritabanı ikili büyük nesneler (BLOB) saklayabilir, ancak BLOB'ları alma çok miktarda bellek kullanabilir.</span><span class="sxs-lookup"><span data-stu-id="f5cde-104">A [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] database can store binary large objects (BLOBs), but retrieving BLOBS can use a lot of memory.</span></span>  
  
 <span data-ttu-id="f5cde-105">Destek ve bu sunucudan giden akış [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] tam olarak daha az bellek taşması özel durumları kaynaklanan belleğe verileri yüklemek zorunda kalmadan veri akış uygulamaları yazma basitleştirir.</span><span class="sxs-lookup"><span data-stu-id="f5cde-105">Streaming support to and from [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] simplifies writing applications that stream data, without having to fully load the data into memory, resulting in fewer memory overflow exceptions.</span></span>  
  
 <span data-ttu-id="f5cde-106">Akış desteği de özellikle iş nesneleri göndermek, almak ve büyük BLOB'ları değiştirmek için SQL Azure eriştikleri senaryolarında daha iyi ölçeklendirme orta katman uygulamaları etkinleştirir.</span><span class="sxs-lookup"><span data-stu-id="f5cde-106">Streaming support will also enable middle-tier applications to scale better, especially in scenarios where business objects connect to SQL Azure in order to send, retrieve, and manipulate large BLOBs.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="f5cde-107">Bir uygulama da kullanıyorsa, zaman uyumsuz çağrıları desteklenmez `Context Connection` bağlantı dizesi anahtar sözcüğü.</span><span class="sxs-lookup"><span data-stu-id="f5cde-107">Asynchronous calls are not supported if an application also uses the `Context Connection` connection string keyword.</span></span>  
>   
>  <span data-ttu-id="f5cde-108">Akış desteklemek için eklenen üyeler sorgularından veri almaya ve sorguları ve saklı yordamlar parametreleri geçirmek için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="f5cde-108">The members added to support streaming are used to retrieve data from queries and to pass parameters to queries and stored procedures.</span></span> <span data-ttu-id="f5cde-109">Akış özelliği temel OLTP ve veri geçişi senaryoları yer almaktadır ve şirket içi ve şirket içi veri migrations.environments kapatmak için geçerlidir.</span><span class="sxs-lookup"><span data-stu-id="f5cde-109">The streaming feature addresses basic OLTP and data migration scenarios and is applicable to on premise and off premise data migrations.environments.</span></span>  
  
## <a name="streaming-support-from-includessnoversionincludesssnoversion-mdmd"></a><span data-ttu-id="f5cde-110">Akış Destek'ten[!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5cde-110">Streaming Support from [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)]</span></span>  
 <span data-ttu-id="f5cde-111">Destek'ten akış [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] yeni işlevselliği sunar <xref:System.Data.Common.DbDataReader> ve <xref:System.Data.SqlClient.SqlDataReader> alabilmek için sınıflar <xref:System.IO.Stream>, <xref:System.Xml.XmlReader>, ve <xref:System.IO.TextReader> nesneleri ve tepki.</span><span class="sxs-lookup"><span data-stu-id="f5cde-111">Streaming support from [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] introduces new functionality in the <xref:System.Data.Common.DbDataReader> and in the <xref:System.Data.SqlClient.SqlDataReader> classes in order to get <xref:System.IO.Stream>, <xref:System.Xml.XmlReader>, and <xref:System.IO.TextReader> objects and react to them.</span></span>  <span data-ttu-id="f5cde-112">Bu sınıfların sorgularından verileri almak için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="f5cde-112">These classes are used to retrieve data from queries.</span></span> <span data-ttu-id="f5cde-113">Sonuç olarak, Destek'ten akış [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] OLTP senaryoları yer almaktadır ve şirket içi ve şirket dışı ortamlar için geçerlidir.</span><span class="sxs-lookup"><span data-stu-id="f5cde-113">As a result, Streaming support from [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] addresses OLTP scenarios and applies to on-premise and off-premise environments.</span></span>  
  
 <span data-ttu-id="f5cde-114">Aşağıdaki üyeleri eklenme <xref:System.Data.SqlClient.SqlDataReader> akış desteğini etkinleştirmek için [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="f5cde-114">The following members were added to <xref:System.Data.SqlClient.SqlDataReader> to enable streaming support from [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)]:</span></span>  
  
1.  <xref:System.Data.SqlClient.SqlDataReader.IsDBNullAsync%2A>  
  
2.  <xref:System.Data.SqlClient.SqlDataReader.GetFieldValue%2A?displayProperty=nameWithType>  
  
3.  <xref:System.Data.SqlClient.SqlDataReader.GetFieldValueAsync%2A>  
  
4.  <xref:System.Data.SqlClient.SqlDataReader.GetStream%2A>  
  
5.  <xref:System.Data.SqlClient.SqlDataReader.GetTextReader%2A>  
  
6.  <xref:System.Data.SqlClient.SqlDataReader.GetXmlReader%2A>  
  
 <span data-ttu-id="f5cde-115">Aşağıdaki üyeleri eklenme <xref:System.Data.Common.DbDataReader> akış desteğini etkinleştirmek için [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="f5cde-115">The following members were added to <xref:System.Data.Common.DbDataReader> to enable streaming support from [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)]:</span></span>  
  
1.  <xref:System.Data.Common.DbDataReader.GetFieldValue%2A>  
  
2.  <xref:System.Data.Common.DbDataReader.GetStream%2A>  
  
3.  <xref:System.Data.Common.DbDataReader.GetTextReader%2A>  
  
## <a name="streaming-support-to-includessnoversionincludesssnoversion-mdmd"></a><span data-ttu-id="f5cde-116">Akış desteği[!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5cde-116">Streaming Support to [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)]</span></span>  
 <span data-ttu-id="f5cde-117">Akış desteği için [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] yeni işlevselliği sunar <xref:System.Data.SqlClient.SqlParameter> kabul edebilir ve tepki şekilde sınıf <xref:System.Xml.XmlReader>, <xref:System.IO.Stream>, ve <xref:System.IO.TextReader> nesneleri.</span><span class="sxs-lookup"><span data-stu-id="f5cde-117">Streaming support to [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] introduces new functionality in the <xref:System.Data.SqlClient.SqlParameter> class so it can accept and react to <xref:System.Xml.XmlReader>, <xref:System.IO.Stream>, and <xref:System.IO.TextReader> objects.</span></span> <span data-ttu-id="f5cde-118"><xref:System.Data.SqlClient.SqlParameter>Parametre sorguları ve saklı yordamlar geçirmek için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="f5cde-118"><xref:System.Data.SqlClient.SqlParameter> is used to pass parameters to queries and stored procedures.</span></span>  
  
 <span data-ttu-id="f5cde-119">Atma bir <xref:System.Data.SqlClient.SqlCommand> nesne veya arama <xref:System.Data.SqlClient.SqlCommand.Cancel%2A> herhangi bir akış işlemi iptal etmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="f5cde-119">Disposing a <xref:System.Data.SqlClient.SqlCommand> object or calling <xref:System.Data.SqlClient.SqlCommand.Cancel%2A> must cancel any streaming operation.</span></span> <span data-ttu-id="f5cde-120">Bir uygulama gönderirse <xref:System.Threading.CancellationToken>, iptal garanti edilmez.</span><span class="sxs-lookup"><span data-stu-id="f5cde-120">If an application sends <xref:System.Threading.CancellationToken>, cancellation is not guaranteed.</span></span>  
  
 <span data-ttu-id="f5cde-121">Aşağıdaki <xref:System.Data.SqlClient.SqlParameter.SqlDbType%2A> türlerini kabul edeceği bir <xref:System.Data.SqlClient.SqlParameter.Value%2A> , <xref:System.IO.Stream>:</span><span class="sxs-lookup"><span data-stu-id="f5cde-121">The following <xref:System.Data.SqlClient.SqlParameter.SqlDbType%2A> types will accept a <xref:System.Data.SqlClient.SqlParameter.Value%2A> of <xref:System.IO.Stream>:</span></span>  
  
-   <span data-ttu-id="f5cde-122">**İkili**</span><span class="sxs-lookup"><span data-stu-id="f5cde-122">**Binary**</span></span>  
  
-   <span data-ttu-id="f5cde-123">**VarBinary**</span><span class="sxs-lookup"><span data-stu-id="f5cde-123">**VarBinary**</span></span>  
  
 <span data-ttu-id="f5cde-124">Aşağıdaki <xref:System.Data.SqlClient.SqlParameter.SqlDbType%2A> türlerini kabul edeceği bir <xref:System.Data.SqlClient.SqlParameter.Value%2A> , <xref:System.IO.TextReader>:</span><span class="sxs-lookup"><span data-stu-id="f5cde-124">The following <xref:System.Data.SqlClient.SqlParameter.SqlDbType%2A> types will accept a <xref:System.Data.SqlClient.SqlParameter.Value%2A> of <xref:System.IO.TextReader>:</span></span>  
  
-   <span data-ttu-id="f5cde-125">**Char**</span><span class="sxs-lookup"><span data-stu-id="f5cde-125">**Char**</span></span>  
  
-   <span data-ttu-id="f5cde-126">**NChar**</span><span class="sxs-lookup"><span data-stu-id="f5cde-126">**NChar**</span></span>  
  
-   <span data-ttu-id="f5cde-127">**NVarChar**</span><span class="sxs-lookup"><span data-stu-id="f5cde-127">**NVarChar**</span></span>  
  
-   <span data-ttu-id="f5cde-128">**XML**</span><span class="sxs-lookup"><span data-stu-id="f5cde-128">**Xml**</span></span>  
  
 <span data-ttu-id="f5cde-129">**Xml** <xref:System.Data.SqlClient.SqlParameter.SqlDbType%2A> türü kabul edeceği bir <xref:System.Data.SqlClient.SqlParameter.Value%2A> , <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="f5cde-129">The **Xml**<xref:System.Data.SqlClient.SqlParameter.SqlDbType%2A> type will accept a <xref:System.Data.SqlClient.SqlParameter.Value%2A> of <xref:System.Xml.XmlReader>.</span></span>  
  
 <span data-ttu-id="f5cde-130"><xref:System.Data.SqlClient.SqlParameter.SqlValue%2A>türündeki değerleri kabul edebilir <xref:System.Xml.XmlReader>, <xref:System.IO.TextReader>, ve <xref:System.IO.Stream>.</span><span class="sxs-lookup"><span data-stu-id="f5cde-130"><xref:System.Data.SqlClient.SqlParameter.SqlValue%2A> can accept values of type <xref:System.Xml.XmlReader>, <xref:System.IO.TextReader>, and <xref:System.IO.Stream>.</span></span>  
  
 <span data-ttu-id="f5cde-131"><xref:System.Xml.XmlReader>, <xref:System.IO.TextReader>, Ve <xref:System.IO.Stream> nesnesi aktarılmayacak kadar tarafından tanımlanan değer <xref:System.Data.SqlClient.SqlParameter.Size%2A>.</span><span class="sxs-lookup"><span data-stu-id="f5cde-131">The <xref:System.Xml.XmlReader>, <xref:System.IO.TextReader>, and <xref:System.IO.Stream> object will be transferred up to the value defined by the <xref:System.Data.SqlClient.SqlParameter.Size%2A>.</span></span>  
  
## <a name="sample----streaming-from-includessnoversionincludesssnoversion-mdmd"></a><span data-ttu-id="f5cde-132">Örnek--gelen akış[!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5cde-132">Sample -- Streaming from [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)]</span></span>  
 <span data-ttu-id="f5cde-133">Aşağıdaki [!INCLUDE[tsql](../../../../includes/tsql-md.md)] örnek veritabanı oluşturmak için:</span><span class="sxs-lookup"><span data-stu-id="f5cde-133">Use the following [!INCLUDE[tsql](../../../../includes/tsql-md.md)] to create the sample database:</span></span>  
  
```  
CREATE DATABASE [Demo]  
GO  
USE [Demo]  
GO  
CREATE TABLE [Streams] (  
[id] INT PRIMARY KEY IDENTITY(1, 1),  
[textdata] NVARCHAR(MAX),  
[bindata] VARBINARY(MAX),  
[xmldata] XML)  
GO  
INSERT INTO [Streams] (textdata, bindata, xmldata) VALUES (N'This is a test', 0x48656C6C6F, N'<test>value</test>')  
INSERT INTO [Streams] (textdata, bindata, xmldata) VALUES (N'Hello, World!', 0x54657374696E67, N'<test>value2</test>')  
INSERT INTO [Streams] (textdata, bindata, xmldata) VALUES (N'Another row', 0x666F6F626172, N'<fff>bbb</fff><fff>bbc</fff>')  
GO  
```  
  
 <span data-ttu-id="f5cde-134">Örnek aşağıdakilerin nasıl yapılacağını gösterir:</span><span class="sxs-lookup"><span data-stu-id="f5cde-134">The sample shows how to do the following:</span></span>  
  
-   <span data-ttu-id="f5cde-135">Büyük dosyaları almak için zaman uyumsuz bir yol sağlayarak bir kullanıcı arabirimi iş parçacığı engelleme kaçının.</span><span class="sxs-lookup"><span data-stu-id="f5cde-135">Avoid blocking a user-interface thread by providing an asynchronous way to retrieve large files.</span></span>  
  
-   <span data-ttu-id="f5cde-136">Büyük metin dosyasından aktarım [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] içinde [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f5cde-136">Transfer a large text file from [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] in [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)].</span></span>  
  
-   <span data-ttu-id="f5cde-137">Büyük bir XML dosyasından aktarım [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] içinde [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f5cde-137">Transfer a large XML file from [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] in [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)].</span></span>  
  
-   <span data-ttu-id="f5cde-138">Verilerin alınacağı [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f5cde-138">Retrieve data from [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="f5cde-139">Büyük dosyaları (BLOB) birinden aktarmak [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] bellek yetersiz çalıştırılmadan başka bir veritabanı.</span><span class="sxs-lookup"><span data-stu-id="f5cde-139">Transfer large files (BLOBs) from one [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] database to another without running out of memory.</span></span>  
  
```  
using System;  
using System.Data;  
using System.Data.SqlClient;  
using System.IO;  
using System.Threading.Tasks;  
using System.Xml;  
  
namespace StreamingFromServer {  
   class Program {  
      // Replace the connection string if needed, for instance to connect to SQL Express: @"Server=(local)\SQLEXPRESS;Database=Demo;Integrated Security=true"  
      private const string connectionString = @"Server=(localdb)\V11.0;Database=Demo";  
  
      static void Main(string[] args) {  
         CopyBinaryValueToFile().Wait();  
         PrintTextValues().Wait();  
         PrintXmlValues().Wait();  
         PrintXmlValuesViaNVarChar().Wait();  
  
         Console.WriteLine("Done");  
      }  
  
      // Application retrieving a large BLOB from SQL Server in .NET 4.5 using the new asynchronous capability  
      private static async Task CopyBinaryValueToFile() {  
         string filePath = Path.Combine(Environment.GetFolderPath(Environment.SpecialFolder.MyDocuments), "binarydata.bin");  
  
         using (SqlConnection connection = new SqlConnection(connectionString)) {  
            await connection.OpenAsync();  
            using (SqlCommand command = new SqlCommand("SELECT [bindata] FROM [Streams] WHERE [id]=@id", connection)) {  
               command.Parameters.AddWithValue("id", 1);  
  
               // The reader needs to be executed with the SequentialAccess behavior to enable network streaming  
               // Otherwise ReadAsync will buffer the entire BLOB into memory which can cause scalability issues or even OutOfMemoryExceptions  
               using (SqlDataReader reader = await command.ExecuteReaderAsync(CommandBehavior.SequentialAccess)) {  
                  if (await reader.ReadAsync()) {  
                     if (!(await reader.IsDBNullAsync(0))) {  
                        using (FileStream file = new FileStream(filePath, FileMode.Create, FileAccess.Write)) {  
                           using (Stream data = reader.GetStream(0)) {  
  
                              // Asynchronously copy the stream from the server to the file we just created  
                              await data.CopyToAsync(file);  
                           }  
                        }  
                     }  
                  }  
               }  
            }  
         }  
      }  
  
      // Application transferring a large Text File from SQL Server in .NET 4.5  
      private static async Task PrintTextValues() {  
         using (SqlConnection connection = new SqlConnection(connectionString)) {  
            await connection.OpenAsync();  
            using (SqlCommand command = new SqlCommand("SELECT [id], [textdata] FROM [Streams]", connection)) {  
  
               // The reader needs to be executed with the SequentialAccess behavior to enable network streaming  
               // Otherwise ReadAsync will buffer the entire text document into memory which can cause scalability issues or even OutOfMemoryExceptions  
               using (SqlDataReader reader = await command.ExecuteReaderAsync(CommandBehavior.SequentialAccess)) {  
                  while (await reader.ReadAsync()) {  
                     Console.Write("{0}: ", reader.GetInt32(0));  
  
                     if (await reader.IsDBNullAsync(1)) {  
                        Console.Write("(NULL)");  
                     }  
                     else {  
                        char[] buffer = new char[4096];  
                        int charsRead = 0;  
                        using (TextReader data = reader.GetTextReader(1)) {  
                           do {  
                              // Grab each chunk of text and write it to the console  
                              // If you are writing to a TextWriter you should use WriteAsync or WriteLineAsync  
                              charsRead = await data.ReadAsync(buffer, 0, buffer.Length);  
                              Console.Write(buffer, 0, charsRead);  
                           } while (charsRead > 0);  
                        }  
                     }  
  
                     Console.WriteLine();  
                  }  
               }  
            }  
         }  
      }  
  
      // Application transferring a large Xml Document from SQL Server in .NET 4.5  
      private static async Task PrintXmlValues() {  
         using (SqlConnection connection = new SqlConnection(connectionString)) {  
            await connection.OpenAsync();  
            using (SqlCommand command = new SqlCommand("SELECT [id], [xmldata] FROM [Streams]", connection)) {  
  
               // The reader needs to be executed with the SequentialAccess behavior to enable network streaming  
               // Otherwise ReadAsync will buffer the entire Xml Document into memory which can cause scalability issues or even OutOfMemoryExceptions  
               using (SqlDataReader reader = await command.ExecuteReaderAsync(CommandBehavior.SequentialAccess)) {  
                  while (await reader.ReadAsync()) {  
                     Console.WriteLine("{0}: ", reader.GetInt32(0));  
  
                     if (await reader.IsDBNullAsync(1)) {  
                        Console.WriteLine("\t(NULL)");  
                     }  
                     else {  
                        using (XmlReader xmlReader = reader.GetXmlReader(1)) {  
                           int depth = 1;  
                           // NOTE: The XmlReader returned by GetXmlReader does NOT support async operations  
                           // See the example below (PrintXmlValuesViaNVarChar) for how to get an XmlReader with asynchronous capabilities  
                           while (xmlReader.Read()) {  
                              switch (xmlReader.NodeType) {  
                                 case XmlNodeType.Element:  
                                    Console.WriteLine("{0}<{1}>", new string('\t', depth), xmlReader.Name);  
                                    depth++;  
                                    break;  
                                 case XmlNodeType.Text:  
                                    Console.WriteLine("{0}{1}", new string('\t', depth), xmlReader.Value);  
                                    break;  
                                 case XmlNodeType.EndElement:  
                                    depth--;  
                                    Console.WriteLine("{0}</{1}>", new string('\t', depth), xmlReader.Name);  
                                    break;  
                              }  
                           }  
                        }  
                     }  
                  }  
               }  
            }  
         }  
      }  
  
      // Application transferring a large Xml Document from SQL Server in .NET 4.5  
      // This goes via NVarChar and TextReader to enable asynchronous reading  
      private static async Task PrintXmlValuesViaNVarChar() {  
         XmlReaderSettings xmlSettings = new XmlReaderSettings() {  
            // Async must be explicitly enabled in the XmlReaderSettings otherwise the XmlReader will throw exceptions when async methods are called  
            Async = true,  
            // Since we will immediately wrap the TextReader we are creating in an XmlReader, we will permit the XmlReader to take care of closing\disposing it  
            CloseInput = true,  
            // If the Xml you are reading is not a valid document (as per http://msdn.microsoft.com/library/6bts1x50.aspx) you will need to set the conformance level to Fragment  
            ConformanceLevel = ConformanceLevel.Fragment  
         };  
  
         using (SqlConnection connection = new SqlConnection(connectionString)) {  
            await connection.OpenAsync();  
  
            // Cast the XML into NVarChar to enable GetTextReader - trying to use GetTextReader on an XML type will throw an exception  
            using (SqlCommand command = new SqlCommand("SELECT [id], CAST([xmldata] AS NVARCHAR(MAX)) FROM [Streams]", connection)) {  
  
               // The reader needs to be executed with the SequentialAccess behavior to enable network streaming  
               // Otherwise ReadAsync will buffer the entire Xml Document into memory which can cause scalability issues or even OutOfMemoryExceptions  
               using (SqlDataReader reader = await command.ExecuteReaderAsync(CommandBehavior.SequentialAccess)) {  
                  while (await reader.ReadAsync()) {  
                     Console.WriteLine("{0}:", reader.GetInt32(0));  
  
                     if (await reader.IsDBNullAsync(1)) {  
                        Console.WriteLine("\t(NULL)");  
                     }  
                     else {  
                        // Grab the row as a TextReader, then create an XmlReader on top of it  
                        // We are not keeping a reference to the TextReader since the XmlReader is created with the "CloseInput" setting (so it will close the TextReader when needed)  
                        using (XmlReader xmlReader = XmlReader.Create(reader.GetTextReader(1), xmlSettings)) {  
                           int depth = 1;  
                           // The XmlReader above now supports asynchronous operations, so we can use ReadAsync here  
                           while (await xmlReader.ReadAsync()) {  
                              switch (xmlReader.NodeType) {  
                                 case XmlNodeType.Element:  
                                    Console.WriteLine("{0}<{1}>", new string('\t', depth), xmlReader.Name);  
                                    depth++;  
                                    break;  
                                 case XmlNodeType.Text:  
                                    // Depending on what your data looks like, you should either use Value or GetValueAsync  
                                    // Value has less overhead (since it doesn't create a Task), but it may also block if additional data is required  
                                    Console.WriteLine("{0}{1}", new string('\t', depth), await xmlReader.GetValueAsync());  
                                    break;  
                                 case XmlNodeType.EndElement:  
                                    depth--;  
                                    Console.WriteLine("{0}</{1}>", new string('\t', depth), xmlReader.Name);  
                                    break;  
                              }  
                           }  
                        }  
                     }  
                  }  
               }  
            }  
         }  
      }  
   }  
}  
```  
  
## <a name="sample----streaming-to-includessnoversionincludesssnoversion-mdmd"></a><span data-ttu-id="f5cde-140">Örnek--akış[!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5cde-140">Sample -- Streaming to [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)]</span></span>  
 <span data-ttu-id="f5cde-141">Aşağıdaki [!INCLUDE[tsql](../../../../includes/tsql-md.md)] örnek veritabanı oluşturmak için:</span><span class="sxs-lookup"><span data-stu-id="f5cde-141">Use the following [!INCLUDE[tsql](../../../../includes/tsql-md.md)] to create the sample database:</span></span>  
  
```  
CREATE DATABASE [Demo2]  
GO  
USE [Demo2]  
GO  
CREATE TABLE [BinaryStreams] (  
[id] INT PRIMARY KEY IDENTITY(1, 1),  
[bindata] VARBINARY(MAX))  
GO  
CREATE TABLE [TextStreams] (  
[id] INT PRIMARY KEY IDENTITY(1, 1),  
[textdata] NVARCHAR(MAX))  
GO  
CREATE TABLE [BinaryStreamsCopy] (  
[id] INT PRIMARY KEY IDENTITY(1, 1),  
[bindata] VARBINARY(MAX))  
GO  
```  
  
 <span data-ttu-id="f5cde-142">Örnek aşağıdakilerin nasıl yapılacağını gösterir:</span><span class="sxs-lookup"><span data-stu-id="f5cde-142">The sample shows how to do the following:</span></span>  
  
-   <span data-ttu-id="f5cde-143">Büyük bir BLOB aktarma [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] içinde [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f5cde-143">Transferring a large BLOB to [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] in [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)].</span></span>  
  
-   <span data-ttu-id="f5cde-144">Bir uzun metin dosyasına aktarılıyor [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] içinde [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f5cde-144">Transferring a large text file to [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] in [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)].</span></span>  
  
-   <span data-ttu-id="f5cde-145">Büyük bir BLOB aktarmak için yeni zaman uyumsuz özelliğini kullanarak.</span><span class="sxs-lookup"><span data-stu-id="f5cde-145">Using the new asynchronous feature to transfer a large BLOB.</span></span>  
  
-   <span data-ttu-id="f5cde-146">Zaman uyumsuz yeni özellik ve bekleme anahtar büyük BLOB aktarmak için kullanma.</span><span class="sxs-lookup"><span data-stu-id="f5cde-146">Using the new asynchronous feature and the await keyword to transfer a large BLOB.</span></span>  
  
-   <span data-ttu-id="f5cde-147">Büyük bir BLOB aktarımını iptal ediliyor...</span><span class="sxs-lookup"><span data-stu-id="f5cde-147">Cancelling the transfer of a large BLOB..</span></span>  
  
-   <span data-ttu-id="f5cde-148">Bir akış [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] başka bir yeni zaman uyumsuz özelliğini kullanarak.</span><span class="sxs-lookup"><span data-stu-id="f5cde-148">Streaming from one [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] to another using the new asynchronous feature.</span></span>  
  
```  
using System;  
using System.Data;  
using System.Data.SqlClient;  
using System.IO;  
using System.Threading;  
using System.Threading.Tasks;  
  
namespace StreamingToServer {  
   class Program {  
      // Replace the connection string if needed, for instance to connect to SQL Express: @"Server=(local)\SQLEXPRESS;Database=Demo2;Integrated Security=true"  
      private const string connectionString = @"Server=(localdb)\V11.0;Database=Demo2";  
  
      static void Main(string[] args) {  
         CreateDemoFiles();  
  
         StreamBLOBToServer().Wait();  
         StreamTextToServer().Wait();  
  
         // Create a CancellationTokenSource that will be cancelled after 100ms  
         // Typically this token source will be cancelled by a user request (e.g. a Cancel button)  
         CancellationTokenSource tokenSource = new CancellationTokenSource();  
         tokenSource.CancelAfter(100);  
         try {  
            CancelBLOBStream(tokenSource.Token).Wait();  
         }  
         catch (AggregateException ex) {  
            // Cancelling an async operation will throw an exception  
            // Since we are using the Task's Wait method, this exception will be wrapped in an AggregateException  
            // If you were using the 'await' keyword, the compiler would take care of unwrapping the AggregateException  
            // Depending on when the cancellation occurs, you can either get an error from SQL Server or from .Net  
            if ((ex.InnerException is SqlException) || (ex.InnerException is TaskCanceledException)) {  
               // This is an expected exception  
               Console.WriteLine("Got expected exception: {0}", ex.InnerException.Message);  
            }  
            else {  
               // Did not expect this exception - re-throw it  
               throw;  
            }  
         }  
  
         Console.WriteLine("Done");  
      }  
  
      // This is used to generate the files which are used by the other sample methods  
      private static void CreateDemoFiles() {  
         Random rand = new Random();  
         byte[] data = new byte[1024];  
         rand.NextBytes(data);  
  
         using (FileStream file = File.Open("binarydata.bin", FileMode.Create)) {  
            file.Write(data, 0, data.Length);  
         }  
  
         using (StreamWriter writer = new StreamWriter(File.Open("textdata.txt", FileMode.Create))) {  
            writer.Write(Convert.ToBase64String(data));  
         }  
      }  
  
      // Application transferring a large BLOB to SQL Server in .Net 4.5  
      private static async Task StreamBLOBToServer() {  
         using (SqlConnection conn = new SqlConnection(connectionString)) {  
            await conn.OpenAsync();  
            using (SqlCommand cmd = new SqlCommand("INSERT INTO [BinaryStreams] (bindata) VALUES (@bindata)", conn)) {  
               using (FileStream file = File.Open("binarydata.bin", FileMode.Open)) {  
  
                  // Add a parameter which uses the FileStream we just opened  
                  // Size is set to -1 to indicate "MAX"  
                  cmd.Parameters.Add("@bindata", SqlDbType.Binary, -1).Value = file;  
  
                  // Send the data to the server asynchronously  
                  await cmd.ExecuteNonQueryAsync();  
               }  
            }  
         }  
      }  
  
      // Application transferring a large Text File to SQL Server in .Net 4.5  
      private static async Task StreamTextToServer() {  
         using (SqlConnection conn = new SqlConnection(connectionString)) {  
            await conn.OpenAsync();  
            using (SqlCommand cmd = new SqlCommand("INSERT INTO [TextStreams] (textdata) VALUES (@textdata)", conn)) {  
               using (StreamReader file = File.OpenText("textdata.txt")) {  
  
                  // Add a parameter which uses the StreamReader we just opened  
                  // Size is set to -1 to indicate "MAX"  
                  cmd.Parameters.Add("@textdata", SqlDbType.NVarChar, -1).Value = file;  
  
                  // Send the data to the server asynchronously  
                  await cmd.ExecuteNonQueryAsync();  
               }  
            }  
         }  
      }  
  
      // Cancelling the transfer of a large BLOB  
      private static async Task CancelBLOBStream(CancellationToken cancellationToken) {  
         using (SqlConnection conn = new SqlConnection(connectionString)) {  
            // We can cancel not only sending the data to the server, but also opening the connection  
            await conn.OpenAsync(cancellationToken);  
  
            // Artifically delay the command by 100ms  
            using (SqlCommand cmd = new SqlCommand("WAITFOR DELAY '00:00:00:100';INSERT INTO [BinaryStreams] (bindata) VALUES (@bindata)", conn)) {  
               using (FileStream file = File.Open("binarydata.bin", FileMode.Open)) {  
  
                  // Add a parameter which uses the FileStream we just opened  
                  // Size is set to -1 to indicate "MAX"  
                  cmd.Parameters.Add("@bindata", SqlDbType.Binary, -1).Value = file;  
  
                  // Send the data to the server asynchronously  
                  // Pass the cancellation token such that the command will be cancelled if needed  
                  await cmd.ExecuteNonQueryAsync(cancellationToken);  
               }  
            }  
         }  
      }  
   }  
}  
```  
  
## <a name="sample----streaming-from-one-includessnoversionincludesssnoversion-mdmd-to-another-includessnoversionincludesssnoversion-mdmd"></a><span data-ttu-id="f5cde-149">Örnek--Birinden akış [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] diğerine[!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5cde-149">Sample -- Streaming From One [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] to Another [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)]</span></span>  
 <span data-ttu-id="f5cde-150">Bu örnek, zaman uyumsuz olarak birinden büyük BLOB akışı gösterilmiştir [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] diğerine iptal desteği.</span><span class="sxs-lookup"><span data-stu-id="f5cde-150">This sample demonstrates how to asynchronously stream a large BLOB from one [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] to another, with support for cancellation.</span></span>  
  
```  
using System;  
using System.Data;  
using System.Data.SqlClient;  
using System.IO;  
using System.Threading;  
using System.Threading.Tasks;  
  
namespace StreamingFromServerToAnother {  
   class Program {  
      // Replace the connection string if needed, for instance to connect to SQL Express: @"Server=(local)\SQLEXPRESS;Database=Demo2;Integrated Security=true"  
      private const string connectionString = @"Server=(localdb)\V11.0;Database=Demo2";  
  
      static void Main(string[] args) {  
         // For this example, we don't want to cancel  
         // So we can pass in a "blank" cancellation token  
         E2EStream(CancellationToken.None).Wait();  
  
         Console.WriteLine("Done");  
      }  
  
      // Streaming from one SQL Server to Another One using the new Async.NET  
      private static async Task E2EStream(CancellationToken cancellationToken) {  
         using (SqlConnection readConn = new SqlConnection(connectionString)) {  
            using (SqlConnection writeConn = new SqlConnection(connectionString)) {  
  
               // Note that we are using the same cancellation token for calls to both connections\commands  
               // Also we can start both the connection opening asynchronously, and then wait for both to complete  
               Task openReadConn = readConn.OpenAsync(cancellationToken);  
               Task openWriteConn = writeConn.OpenAsync(cancellationToken);  
               await Task.WhenAll(openReadConn, openWriteConn);  
  
               using (SqlCommand readCmd = new SqlCommand("SELECT [bindata] FROM [BinaryStreams]", readConn)) {  
                  using (SqlCommand writeCmd = new SqlCommand("INSERT INTO [BinaryStreamsCopy] (bindata) VALUES (@bindata)", writeConn)) {  
  
                     // Add an empty parameter to the write command which will be used for the streams we are copying  
                     // Size is set to -1 to indicate "MAX"  
                     SqlParameter streamParameter = writeCmd.Parameters.Add("@bindata", SqlDbType.Binary, -1);  
  
                     // The reader needs to be executed with the SequentialAccess behavior to enable network streaming  
                     // Otherwise ReadAsync will buffer the entire BLOB into memory which can cause scalability issues or even OutOfMemoryExceptions  
                     using (SqlDataReader reader = await readCmd.ExecuteReaderAsync(CommandBehavior.SequentialAccess, cancellationToken)) {  
                        while (await reader.ReadAsync(cancellationToken)) {  
                           // Grab a stream to the binary data in the source database  
                           using (Stream dataStream = reader.GetStream(0)) {  
  
                              // Set the parameter value to the stream source that was opened  
                              streamParameter.Value = dataStream;  
  
                              // Asynchronously send data from one database to another  
                              await writeCmd.ExecuteNonQueryAsync(cancellationToken);  
                           }  
                        }  
                     }  
                  }  
               }  
            }  
         }  
      }  
   }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="f5cde-151">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="f5cde-151">See Also</span></span>  
 [<span data-ttu-id="f5cde-152">Alma ve ADO.NET veri değiştirme</span><span class="sxs-lookup"><span data-stu-id="f5cde-152">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)