---
title: "Veritabanı şema bilgileri alınıyor"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 79038d52-f122-4fd4-9bfb-aaa22d6a114b
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 71493eb91415b5f4695e771c7a549244629bb654
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="retrieving-database-schema-information"></a><span data-ttu-id="b5862-102">Veritabanı şema bilgileri alınıyor</span><span class="sxs-lookup"><span data-stu-id="b5862-102">Retrieving Database Schema Information</span></span>
<span data-ttu-id="b5862-103">Şema bilgileri veritabanından alma şema bulma işlemi ile gerçekleştirilir.</span><span class="sxs-lookup"><span data-stu-id="b5862-103">Obtaining schema information from a database is accomplished with the process of schema discovery.</span></span> <span data-ttu-id="b5862-104">Şema bulma sağlar yönetilen sağlayıcıları bulmak ve veritabanı şeması hakkında bilgi döndürür olarak da bilinen istemek uygulamalar *meta veri*, belirli bir veritabanı.</span><span class="sxs-lookup"><span data-stu-id="b5862-104">Schema discovery allows applications to request that managed providers find and return information about the database schema, also known as *metadata*, of a given database.</span></span> <span data-ttu-id="b5862-105">Farklı veritabanı şema öğeleri tablolar, sütunlar ve saklı yordamlar gibi şema koleksiyonlarına sunulur.</span><span class="sxs-lookup"><span data-stu-id="b5862-105">Different database schema elements such as tables, columns, and stored-procedures are exposed through schema collections.</span></span> <span data-ttu-id="b5862-106">Her bir şema koleksiyonu şema bilgileri kullanılan sağlayıcıya özgü çeşitli içerir.</span><span class="sxs-lookup"><span data-stu-id="b5862-106">Each schema collection contains a variety of schema information specific to the provider being used.</span></span>  
  
 <span data-ttu-id="b5862-107">.NET Framework yönetilen sağlayıcıları uygulayan her **GetSchema** yönteminde **bağlantı** sınıfı ve sunucudan döndürülen şema bilgileri **GetSchema**yöntemi gelen biçiminde bir <xref:System.Data.DataTable>.</span><span class="sxs-lookup"><span data-stu-id="b5862-107">Each of the .NET Framework managed providers implement the **GetSchema** method in the **Connection** class, and the schema information that is returned from the **GetSchema** method comes in the form of a <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="b5862-108">**GetSchema** dönmek için şema koleksiyonu belirtme ve döndürülen bilgi tutarını sınırlamak için isteğe bağlı parametreler sağlayan bir aşırı yüklenmiş yöntemin bir yöntemdir.</span><span class="sxs-lookup"><span data-stu-id="b5862-108">The **GetSchema** method is an overloaded method that provides optional parameters for specifying the schema collection to return, and restricting the amount of information returned.</span></span>  
  
 <span data-ttu-id="b5862-109">OLE DB, ODBC, Oracle ve SqlClient için .NET Framework veri sağlayıcıları sağlayan bir **GetSchemaTable** sütun meta verileri tanımlayan bir DataTable verir yöntemi **DataReader**.</span><span class="sxs-lookup"><span data-stu-id="b5862-109">The .NET Framework Data Providers for OLE DB, ODBC, Oracle, and SqlClient provide a **GetSchemaTable** method that returns a DataTable describing the column metadata of the **DataReader**.</span></span>  
  
 <span data-ttu-id="b5862-110">Ayrıca OLE DB için .NET Framework veri sağlayıcısı kullanarak şema bilgileri sunan <xref:System.Data.OleDb.OleDbConnection.GetOleDbSchemaTable%2A> yöntemi <xref:System.Data.OleDb.OleDbConnection> nesnesi.</span><span class="sxs-lookup"><span data-stu-id="b5862-110">The .NET Framework Data Provider for OLE DB also exposes schema information by using the <xref:System.Data.OleDb.OleDbConnection.GetOleDbSchemaTable%2A> method of the <xref:System.Data.OleDb.OleDbConnection> object.</span></span> <span data-ttu-id="b5862-111">Bağımsız değişken **GetOleDbSchemaTable** geçen bir <xref:System.Data.OleDb.OleDbSchemaGuid> döndürmek için şema bilgileri tanımlar ve sütunları bu kısıtlamalar bir dizi döndürdü.</span><span class="sxs-lookup"><span data-stu-id="b5862-111">As arguments, **GetOleDbSchemaTable** takes an <xref:System.Data.OleDb.OleDbSchemaGuid> that identifies the schema information to return, and an array of restrictions on those returned columns.</span></span> <span data-ttu-id="b5862-112">**GetOleDbSchemaTable** döndüren bir <xref:System.Data.DataTable> istenen şema bilgileri ile doldurulur.</span><span class="sxs-lookup"><span data-stu-id="b5862-112">**GetOleDbSchemaTable** returns a <xref:System.Data.DataTable> populated with the requested schema information.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b5862-113">Bu Bölümde</span><span class="sxs-lookup"><span data-stu-id="b5862-113">In This Section</span></span>  
 [<span data-ttu-id="b5862-114">GetSchema ve şeması koleksiyonları</span><span class="sxs-lookup"><span data-stu-id="b5862-114">GetSchema and Schema Collections</span></span>](../../../../docs/framework/data/adonet/getschema-and-schema-collections.md)  
 <span data-ttu-id="b5862-115">Açıklar **GetSchema** yöntemi ve nasıl bu almak ve şema bilgilerini veritabanından kısıtlamak için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="b5862-115">Describes the **GetSchema** method and how it can be used to retrieve and restrict schema information from a database.</span></span>  
  
 <span data-ttu-id="b5862-116">Şema kısıtlamaları</span><span class="sxs-lookup"><span data-stu-id="b5862-116">Schema Restrictions</span></span>  
 <span data-ttu-id="b5862-117">İle kullanılan şema kısıtlamaları açıklar **GetSchema**.</span><span class="sxs-lookup"><span data-stu-id="b5862-117">Describes schema restrictions that can be used with **GetSchema**.</span></span>  
  
 [<span data-ttu-id="b5862-118">Ortak şema koleksiyonları</span><span class="sxs-lookup"><span data-stu-id="b5862-118">Common Schema Collections</span></span>](../../../../docs/framework/data/adonet/common-schema-collections.md)  
 <span data-ttu-id="b5862-119">Tüm .NET çerçevesi ile yönetilen sağlayıcılar tarafından desteklenen ortak şeması koleksiyonları tümünün açıklar.</span><span class="sxs-lookup"><span data-stu-id="b5862-119">Describes all of the common schema collections supported by all of the .NET Framework managed providers.</span></span>  
  
 [<span data-ttu-id="b5862-120">SQL Server şeması koleksiyonları</span><span class="sxs-lookup"><span data-stu-id="b5862-120">SQL Server Schema Collections</span></span>](../../../../docs/framework/data/adonet/sql-server-schema-collections.md)  
 <span data-ttu-id="b5862-121">SQL Server için .NET Framework sağlayıcısı tarafından desteklenen şema koleksiyonu açıklar.</span><span class="sxs-lookup"><span data-stu-id="b5862-121">Describes the schema collection supported by the .NET Framework provider for SQL Server.</span></span>  
  
 [<span data-ttu-id="b5862-122">Oracle şema koleksiyonları</span><span class="sxs-lookup"><span data-stu-id="b5862-122">Oracle Schema Collections</span></span>](../../../../docs/framework/data/adonet/oracle-schema-collections.md)  
 <span data-ttu-id="b5862-123">Oracle için .NET Framework sağlayıcısı tarafından desteklenen şema koleksiyonu açıklar.</span><span class="sxs-lookup"><span data-stu-id="b5862-123">Describes the schema collection supported by the .NET Framework provider for Oracle.</span></span>  
  
 [<span data-ttu-id="b5862-124">ODBC şeması koleksiyonları</span><span class="sxs-lookup"><span data-stu-id="b5862-124">ODBC Schema Collections</span></span>](../../../../docs/framework/data/adonet/odbc-schema-collections.md)  
 <span data-ttu-id="b5862-125">ODBC sürücüleri için şema koleksiyonları açıklar.</span><span class="sxs-lookup"><span data-stu-id="b5862-125">Describes the schema collections for ODBC drivers.</span></span>  
  
 [<span data-ttu-id="b5862-126">OLE DB şeması koleksiyonları</span><span class="sxs-lookup"><span data-stu-id="b5862-126">OLE DB Schema Collections</span></span>](../../../../docs/framework/data/adonet/ole-db-schema-collections.md)  
 <span data-ttu-id="b5862-127">OLE DB sağlayıcıları için şema koleksiyonları açıklar.</span><span class="sxs-lookup"><span data-stu-id="b5862-127">Describes the schema collections for OLE DB providers.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="b5862-128">Başvuru</span><span class="sxs-lookup"><span data-stu-id="b5862-128">Reference</span></span>  
 <xref:System.Data.Common.DbConnection.GetSchema%2A>  
 <span data-ttu-id="b5862-129">Açıklar **GetSchema** yöntemi <xref:System.Data.Common.DbConnection> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="b5862-129">Describes the **GetSchema** method of the <xref:System.Data.Common.DbConnection> class.</span></span>  
  
 <xref:System.Data.Odbc.OdbcConnection.GetSchema%2A>  
 <span data-ttu-id="b5862-130">Açıklar **GetSchema** yöntemi <xref:System.Data.Odbc.OdbcConnection> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="b5862-130">Describes the **GetSchema** method of the <xref:System.Data.Odbc.OdbcConnection> class.</span></span>  
  
 <xref:System.Data.OleDb.OleDbConnection.GetSchema%2A>  
 <span data-ttu-id="b5862-131">Açıklar **GetSchema** yöntemi <xref:System.Data.OleDb.OleDbConnection> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="b5862-131">Describes the **GetSchema** method of the <xref:System.Data.OleDb.OleDbConnection> class.</span></span>  
  
 <xref:System.Data.OracleClient.OracleConnection.GetSchema%2A>  
 <span data-ttu-id="b5862-132">Açıklar **GetSchema** yöntemi <xref:System.Data.OracleClient.OracleConnection> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="b5862-132">Describes the **GetSchema** method of the <xref:System.Data.OracleClient.OracleConnection> class.</span></span>  
  
 <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A>  
 <span data-ttu-id="b5862-133">Açıklar **GetSchema** yöntemi <xref:System.Data.SqlClient.SqlConnection> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="b5862-133">Describes the **GetSchema** method of the <xref:System.Data.SqlClient.SqlConnection> class.</span></span>  
  
 <xref:System.Data.Common.DbDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="b5862-134">Açıklar **GetSchemaTable** yöntemi <xref:System.Data.Common.DbDataReader> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="b5862-134">Describes the **GetSchemaTable** method of the <xref:System.Data.Common.DbDataReader> class.</span></span>  
  
 <xref:System.Data.Odbc.OdbcDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="b5862-135">Açıklar **GetSchemaTable** yöntemi <xref:System.Data.Odbc.OdbcDataReader> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="b5862-135">Describes the **GetSchemaTable** method of the <xref:System.Data.Odbc.OdbcDataReader> class.</span></span>  
  
 <xref:System.Data.OleDb.OleDbDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="b5862-136">Açıklar **GetSchemaTable** yöntemi <xref:System.Data.OleDb.OleDbDataReader> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="b5862-136">Describes the **GetSchemaTable** method of the <xref:System.Data.OleDb.OleDbDataReader> class.</span></span>  
  
 <xref:System.Data.OracleClient.OracleDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="b5862-137">Açıklar **GetSchemaTable** yöntemi <xref:System.Data.OracleClient.OracleDataReader> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="b5862-137">Describes the **GetSchemaTable** method of the <xref:System.Data.OracleClient.OracleDataReader> class.</span></span>  
  
 <xref:System.Data.SqlClient.SqlDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="b5862-138">Açıklar **GetSchemaTable** yöntemi <xref:System.Data.SqlClient.SqlDataReader> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="b5862-138">Describes the **GetSchemaTable** method of the <xref:System.Data.SqlClient.SqlDataReader> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5862-139">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="b5862-139">See Also</span></span>  
 [<span data-ttu-id="b5862-140">Alma ve ADO.NET veri değiştirme</span><span class="sxs-lookup"><span data-stu-id="b5862-140">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [<span data-ttu-id="b5862-141">ADO.NET yönetilen sağlayıcıları ve veri kümesi Geliştirici Merkezi</span><span class="sxs-lookup"><span data-stu-id="b5862-141">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)