---
title: Visual Basic'de sorgu yazma
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: get-started-article
helpviewer_keywords:
- queries [LINQ in Visual Basic], writing
- LINQ [Visual Basic], walkthroughs
- LINQ [Visual Basic], writing queries
- writing LINQ queries [Visual Basic]
ms.assetid: f0045808-b9fe-4d31-88d1-473d9957211e
caps.latest.revision: "70"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 00103fe95912ba44a764cef30b337603301c8479
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-writing-queries-in-visual-basic"></a><span data-ttu-id="d740b-102">İzlenecek Yol: Visual Basic'de Sorgu Yazma</span><span class="sxs-lookup"><span data-stu-id="d740b-102">Walkthrough: Writing Queries in Visual Basic</span></span>
<span data-ttu-id="d740b-103">Bu kılavuzda yazmak için Visual Basic dil özellikleri nasıl kullanabileceğinizi gösterir [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] sorgu ifadeleri.</span><span class="sxs-lookup"><span data-stu-id="d740b-103">This walkthrough demonstrates how you can use Visual Basic language features to write [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] query expressions.</span></span> <span data-ttu-id="d740b-104">İzlenecek yol Öğrenci nesnelerin bir listesini sorgu oluşturma, sorguları çalıştırmak nasıl ve bunları değiştirme gösterilir.</span><span class="sxs-lookup"><span data-stu-id="d740b-104">The walkthrough demonstrates how to create queries on a list of Student objects, how to run the queries, and how to modify them.</span></span> <span data-ttu-id="d740b-105">Sorguları nesne başlatıcılar, yerel türü çıkarımı ve anonim türler de dahil olmak üzere çeşitli özellikler dahil.</span><span class="sxs-lookup"><span data-stu-id="d740b-105">The queries incorporate several features including object initializers, local type inference, and anonymous types.</span></span>  
  
 <span data-ttu-id="d740b-106">Bu kılavuzu tamamladıktan sonra örnekler ve belirli belgeler için geçmek hazır olacak [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] ilgilendiğiniz sağlayıcısı.</span><span class="sxs-lookup"><span data-stu-id="d740b-106">After completing this walkthrough, you will be ready to move on to the samples and documentation for the specific [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] provider you are interested in.</span></span> [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]<span data-ttu-id="d740b-107">sağlayıcıları dahil [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)], [!INCLUDE[linq_dataset](~/includes/linq-dataset-md.md)], ve [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d740b-107"> providers include [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)], [!INCLUDE[linq_dataset](~/includes/linq-dataset-md.md)], and [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span></span>  
  
## <a name="create-a-project"></a><span data-ttu-id="d740b-108">Proje oluşturma</span><span class="sxs-lookup"><span data-stu-id="d740b-108">Create a Project</span></span>  
  
#### <a name="to-create-a-console-application-project"></a><span data-ttu-id="d740b-109">Konsol uygulama projesi oluşturmak için</span><span class="sxs-lookup"><span data-stu-id="d740b-109">To create a console application project</span></span>  
  
1.  <span data-ttu-id="d740b-110">Visual Studio'yu başlatın.</span><span class="sxs-lookup"><span data-stu-id="d740b-110">Start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="d740b-111">Üzerinde **dosya** menüsündeki **yeni**ve ardından **proje**.</span><span class="sxs-lookup"><span data-stu-id="d740b-111">On the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="d740b-112">İçinde **yüklü şablonlar** tıklatın **Visual Basic**.</span><span class="sxs-lookup"><span data-stu-id="d740b-112">In the **Installed Templates** list, click **Visual Basic**.</span></span>  
  
4.  <span data-ttu-id="d740b-113">Proje türleri listesinde tıklatın **konsol uygulaması**.</span><span class="sxs-lookup"><span data-stu-id="d740b-113">In the list of project types, click **Console Application**.</span></span> <span data-ttu-id="d740b-114">İçinde **adı** kutusunda, proje için bir ad yazın ve ardından **Tamam**.</span><span class="sxs-lookup"><span data-stu-id="d740b-114">In the **Name** box, type a name for the project, and then click **OK**.</span></span>  
  
     <span data-ttu-id="d740b-115">Bir Proje oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="d740b-115">A project is created.</span></span> <span data-ttu-id="d740b-116">Varsayılan olarak, bu System.Core.dll başvuru içeriyor.</span><span class="sxs-lookup"><span data-stu-id="d740b-116">By default, it contains a reference to System.Core.dll.</span></span> <span data-ttu-id="d740b-117">Ayrıca, **içeri aktarılan ad alanları** listesini [başvurular sayfası, Proje Tasarımcısı (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic) içeren <xref:System.Linq?displayProperty=nameWithType> ad alanı.</span><span class="sxs-lookup"><span data-stu-id="d740b-117">Also, the **Imported namespaces** list on the [References Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic) includes the <xref:System.Linq?displayProperty=nameWithType> namespace.</span></span>  
  
5.  <span data-ttu-id="d740b-118">Üzerinde [derleme sayfası, Proje Tasarımcısı (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic), emin **Option Infer** ayarlanır **üzerinde**.</span><span class="sxs-lookup"><span data-stu-id="d740b-118">On the [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic), ensure that **Option infer** is set to **On**.</span></span>  
  
## <a name="add-an-in-memory-data-source"></a><span data-ttu-id="d740b-119">Bellek İçi Veri Kaynağı ekleme</span><span class="sxs-lookup"><span data-stu-id="d740b-119">Add an In-Memory Data Source</span></span>  
 <span data-ttu-id="d740b-120">Bu kılavuzda sorguları için veri kaynağı listesidir `Student` nesneleri.</span><span class="sxs-lookup"><span data-stu-id="d740b-120">The data source for the queries in this walkthrough is a list of `Student` objects.</span></span> <span data-ttu-id="d740b-121">Her `Student` nesnesini içeren bir ad, Soyadı, bir sınıf yılın ve bir Akademik Öğrenci gövde derece.</span><span class="sxs-lookup"><span data-stu-id="d740b-121">Each `Student` object contains a first name, a last name, a class year, and an academic rank in the student body.</span></span>  
  
#### <a name="to-add-the-data-source"></a><span data-ttu-id="d740b-122">Veri kaynağı eklemek için</span><span class="sxs-lookup"><span data-stu-id="d740b-122">To add the data source</span></span>  
  
-   <span data-ttu-id="d740b-123">Tanımlayan bir `Student` sınıfı ve sınıfının örneklerinin bir listesini oluşturun.</span><span class="sxs-lookup"><span data-stu-id="d740b-123">Define a `Student` class, and create a list of instances of the class.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="d740b-124">Tanımlamak için gerekli kod `Student` sınıfı ve kullanılan liste oluşturma kılavuzda örnekler sağlanır [nasıl yapılır: öğelerinin listesi oluşturma](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md).</span><span class="sxs-lookup"><span data-stu-id="d740b-124">The code needed to define the `Student` class and create the list used in the walkthrough examples is provided in [How to: Create a List of Items](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md).</span></span> <span data-ttu-id="d740b-125">Buradan kopyalayın ve bunu projenize yapıştırın.</span><span class="sxs-lookup"><span data-stu-id="d740b-125">You can copy it from there and paste it into your project.</span></span> <span data-ttu-id="d740b-126">Yeni kodunu projeyi oluşturduğunuzda görünen kodu değiştirir.</span><span class="sxs-lookup"><span data-stu-id="d740b-126">The new code replaces the code that appeared when you created the project.</span></span>  
  
#### <a name="to-add-a-new-student-to-the-students-list"></a><span data-ttu-id="d740b-127">Öğrenciler listesine yeni bir öğrenci eklemek için</span><span class="sxs-lookup"><span data-stu-id="d740b-127">To add a new student to the students list</span></span>  
  
-   <span data-ttu-id="d740b-128">Düzende izleyin `getStudents` başka bir örneği eklemek için yöntemini `Student` listesine sınıfı.</span><span class="sxs-lookup"><span data-stu-id="d740b-128">Follow the pattern in the `getStudents` method to add another instance of the `Student` class to the list.</span></span> <span data-ttu-id="d740b-129">Öğrenci ekleme nesne başlatıcıları tanıtılacaktır.</span><span class="sxs-lookup"><span data-stu-id="d740b-129">Adding the student will introduce you to object initializers.</span></span> <span data-ttu-id="d740b-130">Daha fazla bilgi için bkz: [nesne başlatıcıları: adlandırılmış ve anonim türler](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="d740b-130">For more information, see [Object Initializers: Named and Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md).</span></span>  
  
## <a name="create-a-query"></a><span data-ttu-id="d740b-131">Bir sorgu oluşturun</span><span class="sxs-lookup"><span data-stu-id="d740b-131">Create a Query</span></span>  
 <span data-ttu-id="d740b-132">Çalıştırıldığında, bu bölümde eklenen sorgu, akademik derece bunları ilk on koyar Öğrenciler listesini oluşturur.</span><span class="sxs-lookup"><span data-stu-id="d740b-132">When executed, the query added in this section produces a list of the students whose academic rank puts them in the top ten.</span></span> <span data-ttu-id="d740b-133">Sorgu tam seçer çünkü `Student` her zaman, sorgunun sonuç türü nesnesidir `IEnumerable(Of Student)`.</span><span class="sxs-lookup"><span data-stu-id="d740b-133">Because the query selects the complete `Student` object each time, the type of the query result is `IEnumerable(Of Student)`.</span></span> <span data-ttu-id="d740b-134">Ancak, sorgu türü sorgu tanımlarında genellikle belirtilmedi.</span><span class="sxs-lookup"><span data-stu-id="d740b-134">However, the type of the query typically is not specified in query definitions.</span></span> <span data-ttu-id="d740b-135">Bunun yerine, derleyici yerel türü çıkarımı türü belirlemek için kullanır.</span><span class="sxs-lookup"><span data-stu-id="d740b-135">Instead, the compiler uses local type inference to determine the type.</span></span> <span data-ttu-id="d740b-136">Daha fazla bilgi için bkz: [yerel türü çıkarımı](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span><span class="sxs-lookup"><span data-stu-id="d740b-136">For more information, see [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span> <span data-ttu-id="d740b-137">Sorgunun aralık değişkeni `currentStudent`, her bir başvuru olarak hizmet veren `Student` kaynak örneğinde `students`, her nesnenin özelliklerini erişim sağlayan `students`.</span><span class="sxs-lookup"><span data-stu-id="d740b-137">The query's range variable, `currentStudent`, serves as a reference to each `Student` instance in the source, `students`, providing access to the properties of each object in `students`.</span></span>  
  
#### <a name="to-create-a-simple-query"></a><span data-ttu-id="d740b-138">Basit bir sorgu oluşturmak için</span><span class="sxs-lookup"><span data-stu-id="d740b-138">To create a simple query</span></span>  
  
1.  <span data-ttu-id="d740b-139">Yerinde Bul `Main` şu şekilde işaretlenir projesinin yöntemi:</span><span class="sxs-lookup"><span data-stu-id="d740b-139">Find the place in the `Main` method of the project that is marked as follows:</span></span>  
  
     [!code-vb[VbLINQWalkthrough#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_1.vb)]  
  
     <span data-ttu-id="d740b-140">Aşağıdaki kodu kopyalayın ve yapıştırın.</span><span class="sxs-lookup"><span data-stu-id="d740b-140">Copy the following code and paste it in.</span></span>  
  
     [!code-vb[VbLINQWalkthrough#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_2.vb)]  
  
2.  <span data-ttu-id="d740b-141">Üzerinden fare işaretçisini `studentQuery` derleyici atanan türü olduğunu doğrulamak için kodunuzda `IEnumerable(Of Student)`.</span><span class="sxs-lookup"><span data-stu-id="d740b-141">Rest the mouse pointer over `studentQuery` in your code to verify that the compiler-assigned type is `IEnumerable(Of Student)`.</span></span>  
  
## <a name="run-the-query"></a><span data-ttu-id="d740b-142">Sorguyu çalıştır</span><span class="sxs-lookup"><span data-stu-id="d740b-142">Run the Query</span></span>  
 <span data-ttu-id="d740b-143">Değişkeni `studentQuery` sorgu, sorgu çalıştırmanın sonuçlarını değil tanımını içerir.</span><span class="sxs-lookup"><span data-stu-id="d740b-143">The variable `studentQuery` contains the definition of the query, not the results of running the query.</span></span> <span data-ttu-id="d740b-144">Bir sorgu çalıştırmak için tipik bir mekanizmadır bir `For Each` döngü.</span><span class="sxs-lookup"><span data-stu-id="d740b-144">A typical mechanism for running a query is a `For Each` loop.</span></span> <span data-ttu-id="d740b-145">Döndürülen dizideki her öğe döngü yineleme değişkeni erişilir.</span><span class="sxs-lookup"><span data-stu-id="d740b-145">Each element in the returned sequence is accessed through the loop iteration variable.</span></span> <span data-ttu-id="d740b-146">Sorgu yürütme hakkında daha fazla bilgi için bkz: [yazma bilgisayarınızı ilk LINQ sorgusu](../../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).</span><span class="sxs-lookup"><span data-stu-id="d740b-146">For more information about query execution, see [Writing Your First LINQ Query](../../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).</span></span>  
  
#### <a name="to-run-the-query"></a><span data-ttu-id="d740b-147">Sorguyu çalıştırmak için</span><span class="sxs-lookup"><span data-stu-id="d740b-147">To run the query</span></span>  
  
1.  <span data-ttu-id="d740b-148">Aşağıdakileri ekleyin `For Each` döngü projenizdeki sorgu aşağıda.</span><span class="sxs-lookup"><span data-stu-id="d740b-148">Add the following `For Each` loop below the query in your project.</span></span>  
  
     [!code-vb[VbLINQWalkthrough#3](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_3.vb)]  
  
2.  <span data-ttu-id="d740b-149">For döngüsü denetim değişkeni fare işaretçisini `studentRecord` veri türünü görmek için.</span><span class="sxs-lookup"><span data-stu-id="d740b-149">Rest the mouse pointer over the loop control variable `studentRecord` to see its data type.</span></span> <span data-ttu-id="d740b-150">Türü `studentRecord` olmasını olayla `Student`, çünkü `studentQuery` koleksiyonunu döndürür `Student` örnekleri.</span><span class="sxs-lookup"><span data-stu-id="d740b-150">The type of `studentRecord` is inferred to be `Student`, because `studentQuery` returns a collection of `Student` instances.</span></span>  
  
3.  <span data-ttu-id="d740b-151">Oluşturma ve CTRL + F5'e basarak uygulamayı çalıştırın.</span><span class="sxs-lookup"><span data-stu-id="d740b-151">Build and run the application by pressing CTRL+F5.</span></span> <span data-ttu-id="d740b-152">Sonuçları konsol penceresinde unutmayın.</span><span class="sxs-lookup"><span data-stu-id="d740b-152">Note the results in the console window.</span></span>  
  
## <a name="modify-the-query"></a><span data-ttu-id="d740b-153">Sorguyu Değiştirme</span><span class="sxs-lookup"><span data-stu-id="d740b-153">Modify the Query</span></span>  
 <span data-ttu-id="d740b-154">Belirli bir sırada olmaları durumunda tarama sorgu sonuçlarını daha kolaydır.</span><span class="sxs-lookup"><span data-stu-id="d740b-154">It is easier to scan query results if they are in a specified order.</span></span> <span data-ttu-id="d740b-155">Döndürülen dizi tüm kullanılabilir alana göre sıralayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="d740b-155">You can sort the returned sequence based on any available field.</span></span>  
  
#### <a name="to-order-the-results"></a><span data-ttu-id="d740b-156">Sonuçları sıralamak için</span><span class="sxs-lookup"><span data-stu-id="d740b-156">To order the results</span></span>  
  
1.  <span data-ttu-id="d740b-157">Aşağıdakileri ekleyin `Order By` yan tümcesi arasında `Where` deyimi ve `Select` sorgu ifadesi.</span><span class="sxs-lookup"><span data-stu-id="d740b-157">Add the following `Order By` clause between the `Where` statement and the `Select` statement of the query.</span></span> <span data-ttu-id="d740b-158">`Order By` Yan tümcesi sipariş sonuçları alfabetik olarak A'dan Z'ye, son her öğrencinin adını göre.</span><span class="sxs-lookup"><span data-stu-id="d740b-158">The `Order By` clause will order the results alphabetically from A to Z, according to the last name of each student.</span></span>  
  
    ```  
    Order By currentStudent.Last Ascending   
    ```  
  
2.  <span data-ttu-id="d740b-159">Soyadı ve sonra ilk adına göre sıralamak için her iki alan sorguya ekleyin:</span><span class="sxs-lookup"><span data-stu-id="d740b-159">To order by last name and then first name, add both fields to the query:</span></span>  
  
    ```  
    Order By currentStudent.Last Ascending, currentStudent.First Ascending   
    ```  
  
     <span data-ttu-id="d740b-160">Ayrıca belirtebilirsiniz `Descending` Z siparişe A. için</span><span class="sxs-lookup"><span data-stu-id="d740b-160">You can also specify `Descending` to order from Z to A.</span></span>  
  
3.  <span data-ttu-id="d740b-161">Oluşturma ve CTRL + F5'e basarak uygulamayı çalıştırın.</span><span class="sxs-lookup"><span data-stu-id="d740b-161">Build and run the application by pressing CTRL+F5.</span></span> <span data-ttu-id="d740b-162">Sonuçları konsol penceresinde unutmayın.</span><span class="sxs-lookup"><span data-stu-id="d740b-162">Note the results in the console window.</span></span>  
  
#### <a name="to-introduce-a-local-identifier"></a><span data-ttu-id="d740b-163">Yerel tanımlayıcı tanıtmak için</span><span class="sxs-lookup"><span data-stu-id="d740b-163">To introduce a local identifier</span></span>  
  
1.  <span data-ttu-id="d740b-164">Bu bölümdeki yerel bir tanımlayıcı sorgu ifadesinde tanıtmak için kodu ekleyin.</span><span class="sxs-lookup"><span data-stu-id="d740b-164">Add the code in this section to introduce a local identifier in the query expression.</span></span> <span data-ttu-id="d740b-165">Yerel tanımlayıcı bir ara sonuç tutar.</span><span class="sxs-lookup"><span data-stu-id="d740b-165">The local identifier will hold an intermediate result.</span></span> <span data-ttu-id="d740b-166">Aşağıdaki örnekte, `name` Öğrenci birleşimini tutan bir tanımlayıcı ilk ve son adları.</span><span class="sxs-lookup"><span data-stu-id="d740b-166">In the following example, `name` is an identifier that holds a concatenation of the student's first and last names.</span></span> <span data-ttu-id="d740b-167">Aksi takdirde birden çok kez hesaplanan bir ifadenin sonuçlarını depolayarak performansını artırabilir veya yerel bir tanımlayıcı kolaylık sağlamak için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="d740b-167">A local identifier can be used for convenience, or it can enhance performance by storing the results of an expression that would otherwise be calculated multiple times.</span></span>  
  
     [!code-vb[VbLINQWalkthrough#4](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_4.vb)]  
  
2.  <span data-ttu-id="d740b-168">Oluşturma ve CTRL + F5'e basarak uygulamayı çalıştırın.</span><span class="sxs-lookup"><span data-stu-id="d740b-168">Build and run the application by pressing CTRL+F5.</span></span> <span data-ttu-id="d740b-169">Sonuçları konsol penceresinde unutmayın.</span><span class="sxs-lookup"><span data-stu-id="d740b-169">Note the results in the console window.</span></span>  
  
#### <a name="to-project-one-field-in-the-select-clause"></a><span data-ttu-id="d740b-170">Select yan tümcesinde bir alan planlamak için</span><span class="sxs-lookup"><span data-stu-id="d740b-170">To project one field in the Select clause</span></span>  
  
1.  <span data-ttu-id="d740b-171">Sorguyu eklemek ve `For Each` öğeleri farklı kaynak öğelerinden bir dizi üreten bir sorgu oluşturmak için bu bölümü döngüden.</span><span class="sxs-lookup"><span data-stu-id="d740b-171">Add the query and `For Each` loop from this section to create a query that produces a sequence whose elements differ from the elements in the source.</span></span> <span data-ttu-id="d740b-172">Aşağıdaki örnekte, kaynak topluluğudur `Student` nesneleri, ancak her nesnenin yalnızca bir üye döndürülür: Soyadı olan Garcia Öğrenciler adı.</span><span class="sxs-lookup"><span data-stu-id="d740b-172">In the following example, the source is a collection of `Student` objects, but only one member of each object is returned: the first name of students whose last name is Garcia.</span></span> <span data-ttu-id="d740b-173">Çünkü `currentStudent.First` bir dize veri türü tarafından döndürülen sıra `studentQuery3` olan `IEnumerable(Of String)`, bir dizi dize.</span><span class="sxs-lookup"><span data-stu-id="d740b-173">Because `currentStudent.First` is a string, the data type of the sequence returned by `studentQuery3` is `IEnumerable(Of String)`, a sequence of strings.</span></span> <span data-ttu-id="d740b-174">Önceki örneklerde olduğu gibi bir veri atama türü `studentQuery3` yerel türü çıkarımı kullanarak belirlemek derleyici için bırakılır.</span><span class="sxs-lookup"><span data-stu-id="d740b-174">As in earlier examples, the assignment of a data type for `studentQuery3` is left for the compiler to determine by using local type inference.</span></span>  
  
     [!code-vb[VbLINQWalkthrough#5](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_5.vb)]  
  
2.  <span data-ttu-id="d740b-175">Üzerinden fare işaretçisini `studentQuery3` atanan türü olduğunu doğrulamak için kodunuzda `IEnumerable(Of String)`.</span><span class="sxs-lookup"><span data-stu-id="d740b-175">Rest the mouse pointer over `studentQuery3` in your code to verify that the assigned type is `IEnumerable(Of String)`.</span></span>  
  
3.  <span data-ttu-id="d740b-176">Oluşturma ve CTRL + F5'e basarak uygulamayı çalıştırın.</span><span class="sxs-lookup"><span data-stu-id="d740b-176">Build and run the application by pressing CTRL+F5.</span></span> <span data-ttu-id="d740b-177">Sonuçları konsol penceresinde unutmayın.</span><span class="sxs-lookup"><span data-stu-id="d740b-177">Note the results in the console window.</span></span>  
  
#### <a name="to-create-an-anonymous-type-in-the-select-clause"></a><span data-ttu-id="d740b-178">Select yan tümcesinde anonim bir tür oluşturmak için</span><span class="sxs-lookup"><span data-stu-id="d740b-178">To create an anonymous type in the Select clause</span></span>  
  
1.  <span data-ttu-id="d740b-179">Nasıl anonim türlerini görmek için bu bölümdeki kod sorgularda kullanılan ekleyin.</span><span class="sxs-lookup"><span data-stu-id="d740b-179">Add the code from this section to see how anonymous types are used in queries.</span></span> <span data-ttu-id="d740b-180">Veri kaynağı tam kayıtları yerine birkaç alanları döndürmek istediğinizde sorgularda kullanabilmek (`currentStudent` önceki örneklerde kayıtları) ya da tek alanları (`First` önceki bölümde).</span><span class="sxs-lookup"><span data-stu-id="d740b-180">You use them in queries when you want to return several fields from the data source rather than complete records (`currentStudent` records in previous examples) or single fields (`First` in the preceding section).</span></span> <span data-ttu-id="d740b-181">Sonuçta dahil etmek istediğiniz alanları içeren yeni bir adlandırılmış türü tanımlama yerine alanlarda belirtin `Select` yan tümcesi ve derleyici özelliklerini olarak bu alanlara sahip anonim bir tür oluşturur.</span><span class="sxs-lookup"><span data-stu-id="d740b-181">Instead of defining a new named type that contains the fields you want to include in the result, you specify the fields in the `Select` clause and the compiler creates an anonymous type with those fields as its properties.</span></span> <span data-ttu-id="d740b-182">Daha fazla bilgi için bkz: [anonim türler](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="d740b-182">For more information, see [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>  
  
     <span data-ttu-id="d740b-183">Aşağıdaki örnek adını ve 1 ile 10 akademik derece sırasına göre akademik derece arasındadır seniors derecesini döndüren bir sorgu oluşturur.</span><span class="sxs-lookup"><span data-stu-id="d740b-183">The following example creates a query that returns the name and rank of seniors whose academic rank is between 1 and 10, in order of academic rank.</span></span> <span data-ttu-id="d740b-184">Bu örnekte, türü `studentQuery4` çünkü olayla gerekir `Select` yan tümcesi anonim bir türün bir örneği döndürür ve anonim bir tür kullanılabilir adı yok.</span><span class="sxs-lookup"><span data-stu-id="d740b-184">In this example, the type of `studentQuery4` must be inferred because the `Select` clause returns an instance of an anonymous type, and an anonymous type has no usable name.</span></span>  
  
     [!code-vb[VbLINQWalkthrough#6](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_6.vb)]  
  
2.  <span data-ttu-id="d740b-185">Oluşturma ve CTRL + F5'e basarak uygulamayı çalıştırın.</span><span class="sxs-lookup"><span data-stu-id="d740b-185">Build and run the application by pressing CTRL+F5.</span></span> <span data-ttu-id="d740b-186">Sonuçları konsol penceresinde unutmayın.</span><span class="sxs-lookup"><span data-stu-id="d740b-186">Note the results in the console window.</span></span>  
  
## <a name="additional-examples"></a><span data-ttu-id="d740b-187">Ek Örnekler</span><span class="sxs-lookup"><span data-stu-id="d740b-187">Additional Examples</span></span>  
 <span data-ttu-id="d740b-188">Temel kavramları anladığınıza göre gücü ve esnekliği göstermek için ek örnekler listesi aşağıdadır [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] sorgular.</span><span class="sxs-lookup"><span data-stu-id="d740b-188">Now that you understand the basics, the following is a list of additional examples to illustrate the flexibility and power of [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] queries.</span></span> <span data-ttu-id="d740b-189">Her örneğin ne yaptığını kısa bir açıklaması tarafından gelmelidir.</span><span class="sxs-lookup"><span data-stu-id="d740b-189">Each example is preceded by a brief description of what it does.</span></span> <span data-ttu-id="d740b-190">Fare işaretçisini çıkarılan türü görmek her sorgu için sorgu sonucu değişkeni üzerine bırakın.</span><span class="sxs-lookup"><span data-stu-id="d740b-190">Rest the mouse pointer over the query result variable for each query to see the inferred type.</span></span> <span data-ttu-id="d740b-191">Kullanım bir `For Each` sonuçlar döngü.</span><span class="sxs-lookup"><span data-stu-id="d740b-191">Use a `For Each` loop to produce the results.</span></span>  
  
 [!code-vb[VbLINQWalkthrough#7](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_7.vb)]  
  
## <a name="additional-information"></a><span data-ttu-id="d740b-192">Ek Bilgiler</span><span class="sxs-lookup"><span data-stu-id="d740b-192">Additional Information</span></span>  
 <span data-ttu-id="d740b-193">Sorguları ile çalışmanın temel kavramları hakkında bilgi sahibi olduktan sonra belgeler ve örnekler için belirli türünü okumak hazır [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] ilgilendiğiniz sağlayıcısı:</span><span class="sxs-lookup"><span data-stu-id="d740b-193">After you are familiar with the basic concepts of working with queries, you are ready to read the documentation and samples for the specific type of [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] provider that you are interested in:</span></span>  
  
 [<span data-ttu-id="d740b-194">Nesnelere LINQ</span><span class="sxs-lookup"><span data-stu-id="d740b-194">LINQ to Objects</span></span>](http://msdn.microsoft.com/library/73cafe73-37cf-46e7-bfa7-97c7eea7ced9)  
  
 [<span data-ttu-id="d740b-195">LINQ-SQL</span><span class="sxs-lookup"><span data-stu-id="d740b-195">LINQ to SQL</span></span>](https://msdn.microsoft.com/library/bb386976)  
  
 [<span data-ttu-id="d740b-196">LINQ-XML</span><span class="sxs-lookup"><span data-stu-id="d740b-196">LINQ to XML</span></span>](http://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13)  
  
 [<span data-ttu-id="d740b-197">LINQ-DataSet</span><span class="sxs-lookup"><span data-stu-id="d740b-197">LINQ to DataSet</span></span>](../../../../framework/data/adonet/linq-to-dataset.md)  
  
## <a name="see-also"></a><span data-ttu-id="d740b-198">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="d740b-198">See Also</span></span>  
 [<span data-ttu-id="d740b-199">Dil ile tümleşik sorgu (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d740b-199">Language-Integrated Query (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/index.md)  
 [<span data-ttu-id="d740b-200">Visual Basic'te Lınq'e Başlarken</span><span class="sxs-lookup"><span data-stu-id="d740b-200">Getting Started with LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)  
 [<span data-ttu-id="d740b-201">Yerel tür çıkarımı</span><span class="sxs-lookup"><span data-stu-id="d740b-201">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [<span data-ttu-id="d740b-202">Nesne başlatıcıları: Adlandırılmış ve anonim türler</span><span class="sxs-lookup"><span data-stu-id="d740b-202">Object Initializers: Named and Anonymous Types</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)  
 [<span data-ttu-id="d740b-203">Anonim türler</span><span class="sxs-lookup"><span data-stu-id="d740b-203">Anonymous Types</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)  
 [<span data-ttu-id="d740b-204">Visual Basic'de LINQ'e giriş</span><span class="sxs-lookup"><span data-stu-id="d740b-204">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [<span data-ttu-id="d740b-205">LINQ</span><span class="sxs-lookup"><span data-stu-id="d740b-205">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [<span data-ttu-id="d740b-206">Sorguları</span><span class="sxs-lookup"><span data-stu-id="d740b-206">Queries</span></span>](../../../../visual-basic/language-reference/queries/queries.md)