---
title: "Veritabanı erişimi etkinlikleri"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 174a381e-1343-46a8-a62c-7c2ae2c4f0b2
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 10066c1d5e6bd0d03d91337a2fed987c881b23b6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="database-access-activities"></a><span data-ttu-id="44047-102">Veritabanı erişimi etkinlikleri</span><span class="sxs-lookup"><span data-stu-id="44047-102">Database Access Activities</span></span>
<span data-ttu-id="44047-103">Veritabanı erişimi etkinliklerini, bir iş akışındaki bir veritabanına erişmek izin verir.</span><span class="sxs-lookup"><span data-stu-id="44047-103">Database access activities allow you to access a database within a workflow.</span></span> <span data-ttu-id="44047-104">Bu etkinliklerin almak veya bilgileri değiştirin ve kullanmak için veritabanlarına erişim ver [ADO.NET](http://go.microsoft.com/fwlink/?LinkId=166081) veritabanına erişmek için.</span><span class="sxs-lookup"><span data-stu-id="44047-104">These activities allow accessing databases to retrieve or modify information and use [ADO.NET](http://go.microsoft.com/fwlink/?LinkId=166081) to access the database.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="44047-105">Örnekler, makinenizde zaten yüklü olabilir.</span><span class="sxs-lookup"><span data-stu-id="44047-105">The samples may already be installed on your machine.</span></span> <span data-ttu-id="44047-106">Devam etmeden önce aşağıdaki (varsayılan) dizin denetleyin.</span><span class="sxs-lookup"><span data-stu-id="44047-106">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="44047-107">Bu dizin mevcut değilse (indirme) gidin tüm indirmek için [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] ve [!INCLUDE[wf1](../../../../includes/wf1-md.md)] örnekleri.</span><span class="sxs-lookup"><span data-stu-id="44047-107">If this directory does not exist, go to (download page) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="44047-108">Bu örnek aşağıdaki dizinde bulunur.</span><span class="sxs-lookup"><span data-stu-id="44047-108">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\DbActivities`  
  
## <a name="database-activities"></a><span data-ttu-id="44047-109">Veritabanı etkinlikleri</span><span class="sxs-lookup"><span data-stu-id="44047-109">Database Activities</span></span>  
 <span data-ttu-id="44047-110">Aşağıdaki bölümlerde bu örnekte dahil etkinliklerin listesini ayrıntılı olarak açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="44047-110">The following sections detail the list of activities included in this sample.</span></span>  
  
## <a name="dbupdate"></a><span data-ttu-id="44047-111">DbUpdate</span><span class="sxs-lookup"><span data-stu-id="44047-111">DbUpdate</span></span>  
 <span data-ttu-id="44047-112">(Ekleme, güncelleştirme, silme ve diğer tüm değişiklikleri) veritabanında değişiklik üreten bir SQL sorgusunu çalıştırır.</span><span class="sxs-lookup"><span data-stu-id="44047-112">Executes a SQL query that produces a modification in the database (insert, update, delete, and other modifications).</span></span>  
  
 <span data-ttu-id="44047-113">Bu sınıf, iş zaman uyumsuz olarak gerçekleştirir (öğesinden türetilen <xref:System.Activities.AsyncCodeActivity> ve zaman uyumsuz yeteneklerini kullanır).</span><span class="sxs-lookup"><span data-stu-id="44047-113">This class performs its work asynchronously (it derives from <xref:System.Activities.AsyncCodeActivity> and uses its asynchronous capabilities).</span></span>  
  
 <span data-ttu-id="44047-114">Bağlantı bilgilerini sağlayıcı sabit adı ayarlanarak yapılandırılabilir (`ProviderName`) ve bağlantı dizesini (`ConnectionString`) veya yalnızca bir bağlantı dizesi yapılandırma adı kullanarak (`ConfigFileSectionName`) uygulama yapılandırma dosyasından.</span><span class="sxs-lookup"><span data-stu-id="44047-114">The connection information can be configured by setting a provider invariant name (`ProviderName`) and the connection string (`ConnectionString`) or just using a connection string configuration name (`ConfigFileSectionName`) from the application configuration file.</span></span>  
  
 <span data-ttu-id="44047-115">Yürütülecek sorgu yapılandırılan kendi `Sql` özelliği ve parametreleri üzerinden geçirilir `Parameters` koleksiyonu.</span><span class="sxs-lookup"><span data-stu-id="44047-115">The query to be executed is configured in its `Sql` property and the parameters are passed through the `Parameters` collection.</span></span>  
  
 <span data-ttu-id="44047-116">Sonra `DbUpdate` olan yürütülen, etkilenen kayıtların sayısı döndürülür `AffectedRecords` özelliği.</span><span class="sxs-lookup"><span data-stu-id="44047-116">After `DbUpdate` is executed, the number of affected records is returned in the `AffectedRecords` property.</span></span>  
  
```  
Public class DbUpdate: AsyncCodeActivity  
{  
    [RequiredArgument]  
    [OverloadGroup("ConnectionString")]  
    [DefaultValue(null)]  
    public InArgument<string> ProviderName { get; set; }  
  
    [RequiredArgument]  
    [OverloadGroup("ConnectionString")]  
    [DependsOn("ProviderName")]  
    [DefaultValue(null)]  
    public InArgument<string> ConnectionString { get; set; }  
  
    [RequiredArgument]  
    [OverloadGroup("ConfigFileSectionName")]  
    [DefaultValue(null)]  
    public InArgument<string> ConfigName { get; set; }  
  
    [DefaultValue(null)]  
    public CommandType CommandType { get; set; }  
  
    [RequiredArgument]  
    public InArgument<string> Sql { get; set; }  
  
    [DependsOn("Sql")]  
    [DefaultValue(null)]  
    public IDictionary<string, Argument> Parameters { get; }  
  
    [DependsOn("Parameters")]  
    public OutArgument<int> AffectedRecords { get; set; }       
}  
```  
  
|<span data-ttu-id="44047-117">Bağımsız Değişken</span><span class="sxs-lookup"><span data-stu-id="44047-117">Argument</span></span>|<span data-ttu-id="44047-118">Açıklama</span><span class="sxs-lookup"><span data-stu-id="44047-118">Description</span></span>|  
|-|-|  
|<span data-ttu-id="44047-119">ProviderName</span><span class="sxs-lookup"><span data-stu-id="44047-119">ProviderName</span></span>|<span data-ttu-id="44047-120">ADO.NET sağlayıcı sabit adı.</span><span class="sxs-lookup"><span data-stu-id="44047-120">ADO.NET provider invariant name.</span></span> <span data-ttu-id="44047-121">Bu değişken ayarlanmışsa, sonra `ConnectionString` de ayarlamanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="44047-121">If this argument is set, then the `ConnectionString` must also be set.</span></span>|  
|<span data-ttu-id="44047-122">connectionString</span><span class="sxs-lookup"><span data-stu-id="44047-122">ConnectionString</span></span>|<span data-ttu-id="44047-123">Veritabanına bağlanmak için bağlantı dizesi.</span><span class="sxs-lookup"><span data-stu-id="44047-123">Connection string to connect to the database.</span></span> <span data-ttu-id="44047-124">Bu bağımsız değişken, ayarlanırsa `ProviderName` de ayarlamanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="44047-124">If this argument is set, then `ProviderName` must also be set.</span></span>|  
|<span data-ttu-id="44047-125">ConfigName</span><span class="sxs-lookup"><span data-stu-id="44047-125">ConfigName</span></span>|<span data-ttu-id="44047-126">Bağlantı bilgilerinin depolandığı yapılandırma dosyası bölümün adı.</span><span class="sxs-lookup"><span data-stu-id="44047-126">Name of the configuration file section where the connection information is stored.</span></span> <span data-ttu-id="44047-127">Bu bağımsız değişken ayarlandığında `ProviderName` ve `ConnectionString` gerekli değildir.</span><span class="sxs-lookup"><span data-stu-id="44047-127">When this argument is set `ProviderName` and `ConnectionString` are not required.</span></span>|  
|<span data-ttu-id="44047-128">CommandType</span><span class="sxs-lookup"><span data-stu-id="44047-128">CommandType</span></span>|<span data-ttu-id="44047-129">Tür <xref:System.Data.Common.DbCommand> yürütülecek.</span><span class="sxs-lookup"><span data-stu-id="44047-129">Type of the <xref:System.Data.Common.DbCommand> to be executed.</span></span>|  
|<span data-ttu-id="44047-130">SQL</span><span class="sxs-lookup"><span data-stu-id="44047-130">Sql</span></span>|<span data-ttu-id="44047-131">Çalıştırılacak SQL komutu.</span><span class="sxs-lookup"><span data-stu-id="44047-131">The SQL command to be executed.</span></span>|  
|<span data-ttu-id="44047-132">Parametreler</span><span class="sxs-lookup"><span data-stu-id="44047-132">Parameters</span></span>|<span data-ttu-id="44047-133">SQL sorgu parametreleri topluluğu.</span><span class="sxs-lookup"><span data-stu-id="44047-133">Collection of the parameters of the SQL query.</span></span>|  
|<span data-ttu-id="44047-134">AffectedRecords</span><span class="sxs-lookup"><span data-stu-id="44047-134">AffectedRecords</span></span>|<span data-ttu-id="44047-135">Son işlem tarafından etkilenen kayıtların sayısı.</span><span class="sxs-lookup"><span data-stu-id="44047-135">Number of records affected by the last operation.</span></span>|  
  
## <a name="dbqueryscalar"></a><span data-ttu-id="44047-136">DbQueryScalar</span><span class="sxs-lookup"><span data-stu-id="44047-136">DbQueryScalar</span></span>  
 <span data-ttu-id="44047-137">Veritabanından tek bir değer alır bir sorgu yürütür.</span><span class="sxs-lookup"><span data-stu-id="44047-137">Executes a query that retrieves a single value from the database.</span></span>  
  
 <span data-ttu-id="44047-138">Bu sınıf, iş zaman uyumsuz olarak gerçekleştirir (öğesinden türetilen <xref:System.Activities.AsyncCodeActivity%601> ve zaman uyumsuz yeteneklerini kullanır).</span><span class="sxs-lookup"><span data-stu-id="44047-138">This class performs its work asynchronously (it derives from <xref:System.Activities.AsyncCodeActivity%601> and uses its asynchronous capabilities).</span></span>  
  
 <span data-ttu-id="44047-139">Bağlantı bilgilerini sağlayıcı sabit adı ayarlanarak yapılandırılabilir (`ProviderName`) ve bağlantı dizesini (`ConnectionString`) veya yalnızca bir bağlantı dizesi yapılandırma adı kullanarak (`ConfigFileSectionName`) uygulama yapılandırma dosyasından.</span><span class="sxs-lookup"><span data-stu-id="44047-139">The connection information can be configured by setting a provider invariant name (`ProviderName`) and the connection string (`ConnectionString`) or just using a connection string configuration name (`ConfigFileSectionName`) from the application configuration file.</span></span>  
  
 <span data-ttu-id="44047-140">Yürütülecek sorgu yapılandırılan kendi `Sql` özelliği ve parametreleri üzerinden geçirilir `Parameters` koleksiyonu.</span><span class="sxs-lookup"><span data-stu-id="44047-140">The query to be executed is configured in its `Sql` property and the parameters are passed through the `Parameters` collection.</span></span>  
  
 <span data-ttu-id="44047-141">Sonra `DbQueryScalar` olan yürütülen, skaler döndürülür `Result``out` bağımsız değişkeni (tür `TResult`, diğer bir deyişle taban sınıf içinde tanımlanan <xref:System.Activities.AsyncCodeActivity%601>).</span><span class="sxs-lookup"><span data-stu-id="44047-141">After `DbQueryScalar` is executed, the scalar is returned in the `Result``out` argument (of type `TResult`, that is defined in the base class <xref:System.Activities.AsyncCodeActivity%601>).</span></span>  
  
```  
public class DbQueryScalar<TResult> : AsyncCodeActivity<TResult>  
{  
    // public arguments  
    [RequiredArgument]  
    [OverloadGroup("ConnectionString")]  
    [DefaultValue(null)]  
    public InArgument<string> ProviderName { get; set; }  
  
    [RequiredArgument]  
    [OverloadGroup("ConnectionString")]  
    [DependsOn("ProviderName")]  
    [DefaultValue(null)]  
    public InArgument<string> ConnectionString { get; set; }  
  
    [RequiredArgument]  
    [OverloadGroup("ConfigFileSectionName")]  
    [DefaultValue(null)]  
    public InArgument<string> ConfigName { get; set; }  
  
    [DefaultValue(null)]  
    public CommandType CommandType { get; set; }  
  
    [RequiredArgument]  
    public InArgument<string> Sql { get; set; }  
  
    [DependsOn("Sql")]  
    [DefaultValue(null)]  
    public IDictionary<string, Argument> Parameters { get; }  
}  
```  
  
|<span data-ttu-id="44047-142">Bağımsız Değişken</span><span class="sxs-lookup"><span data-stu-id="44047-142">Argument</span></span>|<span data-ttu-id="44047-143">Açıklama</span><span class="sxs-lookup"><span data-stu-id="44047-143">Description</span></span>|  
|-|-|  
|<span data-ttu-id="44047-144">ProviderName</span><span class="sxs-lookup"><span data-stu-id="44047-144">ProviderName</span></span>|<span data-ttu-id="44047-145">ADO.NET sağlayıcı sabit adı.</span><span class="sxs-lookup"><span data-stu-id="44047-145">ADO.NET provider invariant name.</span></span> <span data-ttu-id="44047-146">Bu değişken ayarlanmışsa, sonra `ConnectionString` de ayarlamanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="44047-146">If this argument is set, then the `ConnectionString` must also be set.</span></span>|  
|<span data-ttu-id="44047-147">connectionString</span><span class="sxs-lookup"><span data-stu-id="44047-147">ConnectionString</span></span>|<span data-ttu-id="44047-148">Veritabanına bağlanmak için bağlantı dizesi.</span><span class="sxs-lookup"><span data-stu-id="44047-148">Connection string to connect to the database.</span></span> <span data-ttu-id="44047-149">Bu bağımsız değişken, ayarlanırsa `ProviderName` de ayarlamanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="44047-149">If this argument is set, then `ProviderName` must also be set.</span></span>|  
|<span data-ttu-id="44047-150">ConfigName</span><span class="sxs-lookup"><span data-stu-id="44047-150">ConfigName</span></span>|<span data-ttu-id="44047-151">Bağlantı bilgilerinin depolandığı yapılandırma dosyası bölümün adı.</span><span class="sxs-lookup"><span data-stu-id="44047-151">Name of the configuration file section where the connection information is stored.</span></span> <span data-ttu-id="44047-152">Bu bağımsız değişken ayarlandığında `ProviderName` ve `ConnectionString` gerekli değildir.</span><span class="sxs-lookup"><span data-stu-id="44047-152">When this argument is set `ProviderName` and `ConnectionString` are not required.</span></span>|  
|<span data-ttu-id="44047-153">CommandType</span><span class="sxs-lookup"><span data-stu-id="44047-153">CommandType</span></span>|<span data-ttu-id="44047-154">Tür <xref:System.Data.Common.DbCommand> yürütülecek.</span><span class="sxs-lookup"><span data-stu-id="44047-154">Type of the <xref:System.Data.Common.DbCommand> to be executed.</span></span>|  
|<span data-ttu-id="44047-155">SQL</span><span class="sxs-lookup"><span data-stu-id="44047-155">Sql</span></span>|<span data-ttu-id="44047-156">Çalıştırılacak SQL komutu.</span><span class="sxs-lookup"><span data-stu-id="44047-156">The SQL command to be executed.</span></span>|  
|<span data-ttu-id="44047-157">Parametreler</span><span class="sxs-lookup"><span data-stu-id="44047-157">Parameters</span></span>|<span data-ttu-id="44047-158">SQL sorgu parametreleri topluluğu.</span><span class="sxs-lookup"><span data-stu-id="44047-158">Collection of the parameters of the SQL query.</span></span>|  
|<span data-ttu-id="44047-159">Sonuç</span><span class="sxs-lookup"><span data-stu-id="44047-159">Result</span></span>|<span data-ttu-id="44047-160">Sorgu yürütüldükten sonra elde edilen sayılabilir.</span><span class="sxs-lookup"><span data-stu-id="44047-160">Scalar that is obtained after the query is executed.</span></span> <span data-ttu-id="44047-161">Bu bağımsız değişken türü ise `TResult`.</span><span class="sxs-lookup"><span data-stu-id="44047-161">This argument is of type `TResult`.</span></span>|  
  
## <a name="dbquery"></a><span data-ttu-id="44047-162">DbQuery</span><span class="sxs-lookup"><span data-stu-id="44047-162">DbQuery</span></span>  
 <span data-ttu-id="44047-163">Nesnelerin bir listesini alır. bir sorgu yürütür.</span><span class="sxs-lookup"><span data-stu-id="44047-163">Executes a query that retrieves a list of objects.</span></span> <span data-ttu-id="44047-164">Bir eşleme işlev sorgu yürütüldükten sonra yürütülür (Bu olabilir <xref:System.Func%601> < `DbDataReader`, `TResult`> veya bir <xref:System.Activities.ActivityFunc%601> < `DbDataReader`, `TResult`>).</span><span class="sxs-lookup"><span data-stu-id="44047-164">After the query is executed, a mapping function is executed (it can be <xref:System.Func%601><`DbDataReader`, `TResult`> or an <xref:System.Activities.ActivityFunc%601><`DbDataReader`, `TResult`>).</span></span> <span data-ttu-id="44047-165">Bu eşleme işlev kayıt alır bir `DbDataReader` ve döndürülecek nesnesine eşler.</span><span class="sxs-lookup"><span data-stu-id="44047-165">This mapping function gets a record in a `DbDataReader` and maps it to the object to be returned.</span></span>  
  
 <span data-ttu-id="44047-166">Bağlantı bilgilerini sağlayıcı sabit adı ayarlanarak yapılandırılabilir (`ProviderName`) ve bağlantı dizesini (`ConnectionString`) veya yalnızca bir bağlantı dizesi yapılandırma adı kullanarak (`ConfigFileSectionName`) uygulama yapılandırma dosyasından.</span><span class="sxs-lookup"><span data-stu-id="44047-166">The connection information can be configured by setting a provider invariant name (`ProviderName`) and the connection string (`ConnectionString`) or just using a connection string configuration name (`ConfigFileSectionName`) from the application configuration file.</span></span>  
  
 <span data-ttu-id="44047-167">Yürütülecek sorgu yapılandırılan kendi `Sql` özelliği ve parametreleri üzerinden geçirilir `Parameters` koleksiyonu.</span><span class="sxs-lookup"><span data-stu-id="44047-167">The query to be executed is configured in its `Sql` property and the parameters are passed through the `Parameters` collection.</span></span>  
  
 <span data-ttu-id="44047-168">SQL sorgusu sonuçlarını kullanarak alınır bir `DbDataReader`.</span><span class="sxs-lookup"><span data-stu-id="44047-168">The results of the SQL query are retrieved using a `DbDataReader`.</span></span> <span data-ttu-id="44047-169">Etkinlik dolaşır `DbDataReader` ve satırları eşler `DbDataReader` örneğine `TResult`.</span><span class="sxs-lookup"><span data-stu-id="44047-169">The activity iterates through the `DbDataReader` and maps the rows in the `DbDataReader` to an instance of `TResult`.</span></span> <span data-ttu-id="44047-170">Kullanıcıyı `DbQuery` eşleme kodu ve bunu iki şekilde yapılır sağlaması gereken: kullanarak bir <xref:System.Func%601> < `DbDataReader`, `TResult`> veya bir <xref:System.Activities.ActivityFunc%601> < `DbDataReader`, `TResult`>.</span><span class="sxs-lookup"><span data-stu-id="44047-170">The user of `DbQuery` has to provide the mapping code and this can be done in two ways: using a <xref:System.Func%601><`DbDataReader`, `TResult`> or an <xref:System.Activities.ActivityFunc%601><`DbDataReader`, `TResult`>.</span></span> <span data-ttu-id="44047-171">İlk durumda eşleme tek bir yürütme pulse içinde yapılır.</span><span class="sxs-lookup"><span data-stu-id="44047-171">In the first case, the map is done in a single pulse of execution.</span></span> <span data-ttu-id="44047-172">Bu nedenle, daha hızlı olur, ancak bu XAML için seri hale getirilemez.</span><span class="sxs-lookup"><span data-stu-id="44047-172">Therefore, it is faster, but this cannot be serialized to XAML.</span></span> <span data-ttu-id="44047-173">En son durumda eşleme birden çok darbelerin gerçekleştirilir.</span><span class="sxs-lookup"><span data-stu-id="44047-173">In the last case, the map is performed in multiple pulses.</span></span> <span data-ttu-id="44047-174">Bu nedenle, bu daha yavaş olabilir ancak için XAML sıralanabilir ve bildirimli olarak yazılan (herhangi bir varolan etkinliği eşlemesinde katılabilir).</span><span class="sxs-lookup"><span data-stu-id="44047-174">Therefore, it might be slower but can be serialized to XAML and authored declaratively (any existing activity can participate in the mapping).</span></span>  
  
```  
public class DbQuery<TResult> : AsyncCodeActivity<IList<TResult>> where TResult : class  
{  
    // public arguments  
    [RequiredArgument]  
    [OverloadGroup("ConnectionString")]  
    [DefaultValue(null)]  
    public InArgument<string> ProviderName { get; set; }  
  
    [RequiredArgument]  
    [OverloadGroup("ConnectionString")]  
    [DependsOn("ProviderName")]  
    [DefaultValue(null)]  
    public InArgument<string> ConnectionString { get; set; }  
  
    [RequiredArgument]  
    [OverloadGroup("ConfigFileSectionName")]  
    [DefaultValue(null)]  
    public InArgument<string> ConfigName { get; set; }  
  
    [DefaultValue(null)]  
    public CommandType CommandType { get; set; }  
  
    [RequiredArgument]  
    public InArgument<string> Sql { get; set; }  
  
    [DependsOn("Sql")]  
    [DefaultValue(null)]  
    public IDictionary<string, Argument> Parameters { get; }  
  
    [OverloadGroup("DirectMapping")]  
    [DefaultValue(null)]  
    public Func<DbDataReader, TResult> Mapper { get; set; }  
  
    [OverloadGroup("MultiplePulseMapping")]  
    [DefaultValue(null)]  
    public ActivityFunc<DbDataReader, TResult> MapperFunc { get; set; }  
}  
```  
  
|<span data-ttu-id="44047-175">Bağımsız Değişken</span><span class="sxs-lookup"><span data-stu-id="44047-175">Argument</span></span>|<span data-ttu-id="44047-176">Açıklama</span><span class="sxs-lookup"><span data-stu-id="44047-176">Description</span></span>|  
|-|-|  
|<span data-ttu-id="44047-177">ProviderName</span><span class="sxs-lookup"><span data-stu-id="44047-177">ProviderName</span></span>|<span data-ttu-id="44047-178">ADO.NET sağlayıcı sabit adı.</span><span class="sxs-lookup"><span data-stu-id="44047-178">ADO.NET provider invariant name.</span></span> <span data-ttu-id="44047-179">Bu değişken ayarlanmışsa, sonra `ConnectionString` de ayarlamanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="44047-179">If this argument is set, then the `ConnectionString` must also be set.</span></span>|  
|<span data-ttu-id="44047-180">connectionString</span><span class="sxs-lookup"><span data-stu-id="44047-180">ConnectionString</span></span>|<span data-ttu-id="44047-181">Veritabanına bağlanmak için bağlantı dizesi.</span><span class="sxs-lookup"><span data-stu-id="44047-181">Connection string to connect to the database.</span></span> <span data-ttu-id="44047-182">Bu bağımsız değişken, ayarlanırsa `ProviderName` de ayarlamanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="44047-182">If this argument is set, then `ProviderName` must also be set.</span></span>|  
|<span data-ttu-id="44047-183">ConfigName</span><span class="sxs-lookup"><span data-stu-id="44047-183">ConfigName</span></span>|<span data-ttu-id="44047-184">Bağlantı bilgilerinin depolandığı yapılandırma dosyası bölümün adı.</span><span class="sxs-lookup"><span data-stu-id="44047-184">Name of the configuration file section where the connection information is stored.</span></span> <span data-ttu-id="44047-185">Bu bağımsız değişken ayarlandığında `ProviderName` ve `ConnectionString` gerekli değildir.</span><span class="sxs-lookup"><span data-stu-id="44047-185">When this argument is set `ProviderName` and `ConnectionString` are not required.</span></span>|  
|<span data-ttu-id="44047-186">CommandType</span><span class="sxs-lookup"><span data-stu-id="44047-186">CommandType</span></span>|<span data-ttu-id="44047-187">Tür <xref:System.Data.Common.DbCommand> yürütülecek.</span><span class="sxs-lookup"><span data-stu-id="44047-187">Type of the <xref:System.Data.Common.DbCommand> to be executed.</span></span>|  
|<span data-ttu-id="44047-188">SQL</span><span class="sxs-lookup"><span data-stu-id="44047-188">Sql</span></span>|<span data-ttu-id="44047-189">Çalıştırılacak SQL komutu.</span><span class="sxs-lookup"><span data-stu-id="44047-189">The SQL command to be executed.</span></span>|  
|<span data-ttu-id="44047-190">Parametreler</span><span class="sxs-lookup"><span data-stu-id="44047-190">Parameters</span></span>|<span data-ttu-id="44047-191">SQL sorgu parametreleri topluluğu.</span><span class="sxs-lookup"><span data-stu-id="44047-191">Collection of the parameters of the SQL query.</span></span>|  
|<span data-ttu-id="44047-192">Eşleyici</span><span class="sxs-lookup"><span data-stu-id="44047-192">Mapper</span></span>|<span data-ttu-id="44047-193">İşlev eşleme (<xref:System.Func%601><`DbDataReader`, `TResult`>) bir kayıt alan `DataReader` sorgu yürütülürken zaman alınabilir ve türünde bir nesne örneğini döndürür `TResult` eklemekiçin`Result` koleksiyonu.</span><span class="sxs-lookup"><span data-stu-id="44047-193">Mapping function (<xref:System.Func%601><`DbDataReader`, `TResult`>) that takes a record in the `DataReader` obtained as result of executing the query and returns an instance of an object of type `TResult` to be added to the `Result` collection.</span></span><br /><br /> <span data-ttu-id="44047-194">Bu durumda, eşleme tek bir yürütme pulse içinde yapılır, ancak bildirimli olarak Tasarımcısı'nı kullanarak yazılmayı olamaz.</span><span class="sxs-lookup"><span data-stu-id="44047-194">In this case, mapping is done in a single pulse of execution, but it cannot be authored declaratively using the designer.</span></span>|  
|<span data-ttu-id="44047-195">MapperFunc</span><span class="sxs-lookup"><span data-stu-id="44047-195">MapperFunc</span></span>|<span data-ttu-id="44047-196">İşlev eşleme (<xref:System.Activities.ActivityFunc%601><`DbDataReader`, `TResult`>) bir kayıt alan `DataReader` sorgu yürütülürken zaman alınabilir ve türünde bir nesne örneğini döndürür `TResult` eklemekiçin`Result` koleksiyonu.</span><span class="sxs-lookup"><span data-stu-id="44047-196">Mapping function (<xref:System.Activities.ActivityFunc%601><`DbDataReader`, `TResult`>) that takes a record in the `DataReader` obtained as result of executing the query and returns an instance of an object of type `TResult` to be added to the `Result` collection.</span></span><br /><br /> <span data-ttu-id="44047-197">Bu durumda, eşleme yürütme birden çok darbelerin yapılır.</span><span class="sxs-lookup"><span data-stu-id="44047-197">In this case, the mapping is done in multiple pulses of execution.</span></span> <span data-ttu-id="44047-198">Bu işlev için XAML sıralanabilir ve bildirimli olarak yazılan (herhangi bir varolan etkinliği eşlemesinde katılabilir).</span><span class="sxs-lookup"><span data-stu-id="44047-198">This function can be serialized to XAML and authored declaratively (any existing activity can participate in the mapping).</span></span>|  
|<span data-ttu-id="44047-199">Sonuç</span><span class="sxs-lookup"><span data-stu-id="44047-199">Result</span></span>|<span data-ttu-id="44047-200">Nesnelerinin listesi elde sorgu yürütülürken ve her kayıt için eşleme işlev yürütülürken zaman `DataReader`.</span><span class="sxs-lookup"><span data-stu-id="44047-200">List of objects obtained as result of executing the query and executing the mapping function for each record in the `DataReader`.</span></span>|  
  
## <a name="dbquerydataset"></a><span data-ttu-id="44047-201">DbQueryDataSet</span><span class="sxs-lookup"><span data-stu-id="44047-201">DbQueryDataSet</span></span>  
 <span data-ttu-id="44047-202">Döndüren bir sorgu yürüten bir <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="44047-202">Executes a query that returns a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="44047-203">Bu sınıf, iş zaman uyumsuz olarak gerçekleştirir.</span><span class="sxs-lookup"><span data-stu-id="44047-203">This class performs its work asynchronously.</span></span> <span data-ttu-id="44047-204">Öğesinden türetilen <xref:System.Activities.AsyncCodeActivity> < `TResult`> ve zaman uyumsuz yeteneklerini kullanır.</span><span class="sxs-lookup"><span data-stu-id="44047-204">It derives from <xref:System.Activities.AsyncCodeActivity><`TResult`> and uses its asynchronous capabilities.</span></span>  
  
 <span data-ttu-id="44047-205">Bağlantı bilgilerini sağlayıcı sabit adı ayarlanarak yapılandırılabilir (`ProviderName`) ve bağlantı dizesini (`ConnectionString`) veya yalnızca bir bağlantı dizesi yapılandırma adı kullanarak (`ConfigFileSectionName`) uygulama yapılandırma dosyasından.</span><span class="sxs-lookup"><span data-stu-id="44047-205">The connection information can be configured by setting a provider invariant name (`ProviderName`) and the connection string (`ConnectionString`) or just using a connection string configuration name (`ConfigFileSectionName`) from the application configuration file.</span></span>  
  
 <span data-ttu-id="44047-206">Yürütülecek sorgu yapılandırılan kendi `Sql` özelliği ve parametreleri üzerinden geçirilir `Parameters` koleksiyonu.</span><span class="sxs-lookup"><span data-stu-id="44047-206">The query to be executed is configured in its `Sql` property and the parameters are passed through the `Parameters` collection.</span></span>  
  
 <span data-ttu-id="44047-207">Sonra `DbQueryDataSet` yürütülür `DataSet` döndürülür `Result``out` bağımsız değişkeni (tür `TResult`, diğer bir deyişle taban sınıf içinde tanımlanan <xref:System.Activities.AsyncCodeActivity%601>).</span><span class="sxs-lookup"><span data-stu-id="44047-207">After the `DbQueryDataSet` is executed the `DataSet` is returned in the `Result``out` argument (of type `TResult`, that is defined in the base class <xref:System.Activities.AsyncCodeActivity%601>).</span></span>  
  
```  
public class DbQueryDataSet : AsyncCodeActivity<DataSet>  
{  
    // public arguments  
    [RequiredArgument]  
    [OverloadGroup("ConnectionString")]  
    [DefaultValue(null)]  
    public InArgument<string> ProviderName { get; set; }  
  
    [RequiredArgument]  
    [OverloadGroup("ConnectionString")]  
    [DependsOn("ProviderName")]  
    [DefaultValue(null)]  
    public InArgument<string> ConnectionString { get; set; }  
  
    [RequiredArgument]  
    [OverloadGroup("ConfigFileSectionName")]  
    [DefaultValue(null)]  
    public InArgument<string> ConfigName { get; set; }  
  
    [DefaultValue(null)]  
    public CommandType CommandType { get; set; }  
  
    [RequiredArgument]  
    public InArgument<string> Sql { get; set; }  
  
    [DependsOn("Sql")]  
    [DefaultValue(null)]  
    public IDictionary<string, Argument> Parameters { get; }  
}  
```  
  
|<span data-ttu-id="44047-208">Bağımsız Değişken</span><span class="sxs-lookup"><span data-stu-id="44047-208">Argument</span></span>|<span data-ttu-id="44047-209">Açıklama</span><span class="sxs-lookup"><span data-stu-id="44047-209">Description</span></span>|  
|-|-|  
|<span data-ttu-id="44047-210">ProviderName</span><span class="sxs-lookup"><span data-stu-id="44047-210">ProviderName</span></span>|<span data-ttu-id="44047-211">ADO.NET sağlayıcı sabit adı.</span><span class="sxs-lookup"><span data-stu-id="44047-211">ADO.NET provider invariant name.</span></span> <span data-ttu-id="44047-212">Bu değişken ayarlanmışsa, sonra `ConnectionString` de ayarlamanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="44047-212">If this argument is set, then the `ConnectionString` must also be set.</span></span>|  
|<span data-ttu-id="44047-213">connectionString</span><span class="sxs-lookup"><span data-stu-id="44047-213">ConnectionString</span></span>|<span data-ttu-id="44047-214">Veritabanına bağlanmak için bağlantı dizesi.</span><span class="sxs-lookup"><span data-stu-id="44047-214">Connection string to connect to the database.</span></span> <span data-ttu-id="44047-215">Bu bağımsız değişken, ayarlanırsa `ProviderName` de ayarlamanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="44047-215">If this argument is set, then `ProviderName` must also be set.</span></span>|  
|<span data-ttu-id="44047-216">ConfigName</span><span class="sxs-lookup"><span data-stu-id="44047-216">ConfigName</span></span>|<span data-ttu-id="44047-217">Bağlantı bilgilerinin depolandığı yapılandırma dosyası bölümün adı.</span><span class="sxs-lookup"><span data-stu-id="44047-217">Name of the configuration file section where the connection information is stored.</span></span> <span data-ttu-id="44047-218">Bu bağımsız değişken ayarlandığında `ProviderName` ve `ConnectionString` gerekli değildir.</span><span class="sxs-lookup"><span data-stu-id="44047-218">When this argument is set `ProviderName` and `ConnectionString` are not required.</span></span>|  
|<span data-ttu-id="44047-219">CommandType</span><span class="sxs-lookup"><span data-stu-id="44047-219">CommandType</span></span>|<span data-ttu-id="44047-220">Tür <xref:System.Data.Common.DbCommand> yürütülecek.</span><span class="sxs-lookup"><span data-stu-id="44047-220">Type of the <xref:System.Data.Common.DbCommand> to be executed.</span></span>|  
|<span data-ttu-id="44047-221">SQL</span><span class="sxs-lookup"><span data-stu-id="44047-221">Sql</span></span>|<span data-ttu-id="44047-222">Çalıştırılacak SQL komutu.</span><span class="sxs-lookup"><span data-stu-id="44047-222">The SQL command to be executed.</span></span>|  
|<span data-ttu-id="44047-223">Parametreler</span><span class="sxs-lookup"><span data-stu-id="44047-223">Parameters</span></span>|<span data-ttu-id="44047-224">SQL sorgu parametreleri topluluğu.</span><span class="sxs-lookup"><span data-stu-id="44047-224">Collection of the parameters of the SQL query.</span></span>|  
|<span data-ttu-id="44047-225">Sonuç</span><span class="sxs-lookup"><span data-stu-id="44047-225">Result</span></span>|<span data-ttu-id="44047-226"><xref:System.Data.DataSet>Sorgu yürütüldükten sonra elde edilir.</span><span class="sxs-lookup"><span data-stu-id="44047-226"><xref:System.Data.DataSet> that is obtained after the query is executed.</span></span>|  
  
## <a name="configuring-connection-information"></a><span data-ttu-id="44047-227">Bağlantı bilgilerini yapılandırma</span><span class="sxs-lookup"><span data-stu-id="44047-227">Configuring Connection Information</span></span>  
 <span data-ttu-id="44047-228">Tüm DbActivities aynı yapılandırma parametreleri paylaşır.</span><span class="sxs-lookup"><span data-stu-id="44047-228">All DbActivities share the same configuration parameters.</span></span> <span data-ttu-id="44047-229">İki şekilde yapılandırılabilir:</span><span class="sxs-lookup"><span data-stu-id="44047-229">They can be configured in two ways:</span></span>  
  
-   <span data-ttu-id="44047-230">`ConnectionString + InvariantName`: ADO.NET sağlayıcısı değişmez adını ve bağlantı dizesini ayarlayın.</span><span class="sxs-lookup"><span data-stu-id="44047-230">`ConnectionString + InvariantName`: Set the ADO.NET provider invariant name and connection string.</span></span>  
  
    ```  
    Activity dbSelectCount = new DbQueryScalar<DateTime>()  
    {  
        ProviderName = "System.Data.SqlClient",  
        ConnectionString = @"Data Source=.\SQLExpress;  
                             Initial Catalog=DbActivitiesSample;  
                             Integrated Security=True",  
        Sql = "SELECT GetDate()"  
    };  
    ```  
  
-   <span data-ttu-id="44047-231">`ConfigName`: Bağlantı bilgilerini içeren yapılandırma bölümünün adını ayarlayın.</span><span class="sxs-lookup"><span data-stu-id="44047-231">`ConfigName`: Set the name of the configuration section that contains the connection information.</span></span>  
  
    ```xml  
    <connectionStrings>      
        <add name="DbActivitiesSample"  
             providerName="System.Data.SqlClient"  
             connectionString="Data Source=.\SQLExpress;Initial Catalog=DbActivitiesSample;Integrated Security=true"/>  
      </connectionStrings>  
    ```  
  
-   <span data-ttu-id="44047-232">Etkinliğin:</span><span class="sxs-lookup"><span data-stu-id="44047-232">In the activity:</span></span>  
  
    ```  
    Activity dbSelectCount = new DbQueryScalar<int>()  
    {                  
        ConfigName = "DbActivitiesSample",  
        Sql = "SELECT COUNT(*) FROM Roles"  
    };  
    ```  
  
## <a name="running-this-sample"></a><span data-ttu-id="44047-233">Bu örnek çalışıyor</span><span class="sxs-lookup"><span data-stu-id="44047-233">Running this sample</span></span>  
  
### <a name="setup-instructions"></a><span data-ttu-id="44047-234">Kurulum yönergeleri</span><span class="sxs-lookup"><span data-stu-id="44047-234">Setup instructions</span></span>  
 <span data-ttu-id="44047-235">Bu örnek bir veritabanı kullanır.</span><span class="sxs-lookup"><span data-stu-id="44047-235">This sample uses a database.</span></span> <span data-ttu-id="44047-236">Kurulum ve yükleme komut dosyası (Setup.cmd) örneği ile sağlanır.</span><span class="sxs-lookup"><span data-stu-id="44047-236">A set-up and load script (Setup.cmd) is provided with the sample.</span></span> <span data-ttu-id="44047-237">Komut istemini kullanarak bu dosyayı yürütmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="44047-237">You must execute that file using the command prompt.</span></span>  
  
 <span data-ttu-id="44047-238">Setup.cmd komut dosyası şunları SQL komutlarını içeren CreateDb.sql komut dosyasını çağırır:</span><span class="sxs-lookup"><span data-stu-id="44047-238">The Setup.cmd script invokes the CreateDb.sql script file, which contains SQL commands that do the following:</span></span>  
  
-   <span data-ttu-id="44047-239">DbActivitiesSample adlı bir veritabanı oluşturur.</span><span class="sxs-lookup"><span data-stu-id="44047-239">Creates a database called DbActivitiesSample.</span></span>  
  
-   <span data-ttu-id="44047-240">Rolleri tablosu oluşturur.</span><span class="sxs-lookup"><span data-stu-id="44047-240">Creates the Roles table.</span></span>  
  
-   <span data-ttu-id="44047-241">Çalışanlar bir tablo oluşturur.</span><span class="sxs-lookup"><span data-stu-id="44047-241">Creates Employees table.</span></span>  
  
-   <span data-ttu-id="44047-242">Üç kayıt rolleri tabloya ekler.</span><span class="sxs-lookup"><span data-stu-id="44047-242">Inserts three records into the Roles table.</span></span>  
  
-   <span data-ttu-id="44047-243">On iki kayıtları çalışanların tabloya ekler.</span><span class="sxs-lookup"><span data-stu-id="44047-243">Inserts twelve records into the Employees table.</span></span>  
  
##### <a name="to-run-setupcmd"></a><span data-ttu-id="44047-244">Setup.cmd çalıştırmak için</span><span class="sxs-lookup"><span data-stu-id="44047-244">To run Setup.cmd</span></span>  
  
1.  <span data-ttu-id="44047-245">Bir komut istemi açın.</span><span class="sxs-lookup"><span data-stu-id="44047-245">Open a command prompt.</span></span>  
  
2.  <span data-ttu-id="44047-246">DbActivities örnek klasöre gidin.</span><span class="sxs-lookup"><span data-stu-id="44047-246">Go to the DbActivities sample folder.</span></span>  
  
3.  <span data-ttu-id="44047-247">"Setup.cmd" yazın ve ENTER tuşuna basın.</span><span class="sxs-lookup"><span data-stu-id="44047-247">Type "setup.cmd" and press ENTER.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="44047-248">Setup.cmd örnek yerel makine SqlExpress örneğinizi yüklemeyi dener.</span><span class="sxs-lookup"><span data-stu-id="44047-248">Setup.cmd attempts to install the sample in your local machine SqlExpress instance.</span></span> <span data-ttu-id="44047-249">Diğer SQL server örneği yüklemek istiyorsanız, yeni örnek adıyla Setup.cmd düzenleyin.</span><span class="sxs-lookup"><span data-stu-id="44047-249">If you want to install it in other SQL server instance, edit Setup.cmd with the new instance name.</span></span>  
  
##### <a name="to-uninstall-the-sample-database"></a><span data-ttu-id="44047-250">Örnek veritabanını kaldırmak için</span><span class="sxs-lookup"><span data-stu-id="44047-250">To uninstall the sample database</span></span>  
  
1.  <span data-ttu-id="44047-251">Bir komut istemi örnek klasöründeki CleanUp.cmd çalıştırın.</span><span class="sxs-lookup"><span data-stu-id="44047-251">Run Cleanup.cmd from the sample folder in a command prompt.</span></span>  
  
##### <a name="to-run-the-sample"></a><span data-ttu-id="44047-252">Örnek çalıştırmak için</span><span class="sxs-lookup"><span data-stu-id="44047-252">To run the sample</span></span>  
  
1.  <span data-ttu-id="44047-253">Bir çözüm açın[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44047-253">Open the solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]</span></span>  
  
2.  <span data-ttu-id="44047-254">Çözümü derlemek için CTRL + SHIFT + B tuşuna basın.</span><span class="sxs-lookup"><span data-stu-id="44047-254">To compile the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="44047-255">Hata ayıklama olmadan örneği çalıştırmak için CTRL + F5 tuşuna basın.</span><span class="sxs-lookup"><span data-stu-id="44047-255">To run the sample without debugging, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="44047-256">Örnekler, makinenizde zaten yüklü olabilir.</span><span class="sxs-lookup"><span data-stu-id="44047-256">The samples may already be installed on your machine.</span></span> <span data-ttu-id="44047-257">Devam etmeden önce aşağıdaki (varsayılan) dizin denetleyin.</span><span class="sxs-lookup"><span data-stu-id="44047-257">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="44047-258">Bu dizin mevcut değilse, Git [Windows Communication Foundation (WCF) ve .NET Framework 4 için Windows Workflow Foundation (WF) örnek](http://go.microsoft.com/fwlink/?LinkId=150780) tüm indirmek için [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] ve [!INCLUDE[wf1](../../../../includes/wf1-md.md)] örnekleri.</span><span class="sxs-lookup"><span data-stu-id="44047-258">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="44047-259">Bu örnek aşağıdaki dizinde bulunur.</span><span class="sxs-lookup"><span data-stu-id="44047-259">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\DbActivities`