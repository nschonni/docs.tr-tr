---
title: "Tam (Visual Basic) biridir sonra geri kalan zaman uyumsuz görevleri iptal etme"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c928b5a1-622f-4441-8baf-adca1dde197f
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 698ccf5901a77438368b9bf768b88ca6f90fdcbe
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="cancel-remaining-async-tasks-after-one-is-complete-visual-basic"></a><span data-ttu-id="0285c-102">Tam (Visual Basic) biridir sonra geri kalan zaman uyumsuz görevleri iptal etme</span><span class="sxs-lookup"><span data-stu-id="0285c-102">Cancel Remaining Async Tasks after One Is Complete (Visual Basic)</span></span>
<span data-ttu-id="0285c-103">Kullanarak <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> yöntemi ile birlikte bir <xref:System.Threading.CancellationToken>, bir görev tamamlandığında, kalan tüm görevler iptal edebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="0285c-103">By using the <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> method together with a <xref:System.Threading.CancellationToken>, you can cancel all remaining tasks when one task is complete.</span></span> <span data-ttu-id="0285c-104">`WhenAny` Yöntemi görevleri koleksiyonu olmayan bir bağımsız değişken alır.</span><span class="sxs-lookup"><span data-stu-id="0285c-104">The `WhenAny` method takes an argument that’s a collection of tasks.</span></span> <span data-ttu-id="0285c-105">Bu yöntem, tüm görevleri başlatır ve tek bir görev döndürür.</span><span class="sxs-lookup"><span data-stu-id="0285c-105">The method starts all the tasks and returns a single task.</span></span> <span data-ttu-id="0285c-106">Koleksiyondaki herhangi bir görev tamamlandığında, tek bir görev tamamlanır.</span><span class="sxs-lookup"><span data-stu-id="0285c-106">The single task is complete when any task in the collection is complete.</span></span>  
  
 <span data-ttu-id="0285c-107">Bu örnek bir iptal belirteci ile birlikte kullanımı gösterilmiştir `WhenAny` için ilk görev görevler koleksiyonundan tamamlamak için ve diğer görevleri iptal etmek için tutmak için.</span><span class="sxs-lookup"><span data-stu-id="0285c-107">This example demonstrates how to use a cancellation token in conjunction with `WhenAny` to hold onto the first task to finish from the collection of tasks and to cancel the remaining tasks.</span></span> <span data-ttu-id="0285c-108">Her görev, bir Web sitesi içeriğini indirir.</span><span class="sxs-lookup"><span data-stu-id="0285c-108">Each task downloads the contents of a website.</span></span> <span data-ttu-id="0285c-109">Örnek tamamlamak için ilk yükleme içeriğini uzunluğu görüntüler ve diğer yüklemeleri iptal eder.</span><span class="sxs-lookup"><span data-stu-id="0285c-109">The example displays the length of the contents of the first download to complete and cancels the other downloads.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0285c-110">Örnekleri çalıştırmak için Visual Studio 2012 veya daha yeni ve .NET Framework 4.5 olmalıdır veya daha yeni bilgisayarınızda yüklü.</span><span class="sxs-lookup"><span data-stu-id="0285c-110">To run the examples, you must have Visual Studio 2012 or newer and the .NET Framework 4.5 or newer installed on your computer.</span></span>  
  
## <a name="downloading-the-example"></a><span data-ttu-id="0285c-111">Örnek indirme</span><span class="sxs-lookup"><span data-stu-id="0285c-111">Downloading the Example</span></span>  
 <span data-ttu-id="0285c-112">Tam Windows Presentation Foundation (WPF) projeden indirebilirsiniz [zaman uyumsuz örnek: ince ayar uygulamanız](http://go.microsoft.com/fwlink/?LinkId=255046) ve ardından aşağıdaki adımları izleyin.</span><span class="sxs-lookup"><span data-stu-id="0285c-112">You can download the complete Windows Presentation Foundation (WPF) project from [Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046) and then follow these steps.</span></span>  
  
1.  <span data-ttu-id="0285c-113">İndirdiğiniz dosyanın sıkıştırmasını ve Visual Studio'yu başlatın.</span><span class="sxs-lookup"><span data-stu-id="0285c-113">Decompress the file that you downloaded, and then start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="0285c-114">Menü çubuğunda seçin **dosya**, **açık**, **proje/çözüm**.</span><span class="sxs-lookup"><span data-stu-id="0285c-114">On the menu bar, choose **File**, **Open**, **Project/Solution**.</span></span>  
  
3.  <span data-ttu-id="0285c-115">İçinde **Proje Aç** iletişim kutusunda, sıkıştırması örnek kod tutan klasörü açın ve ardından AsyncFineTuningVB için çözüm (.sln) dosyasını açın.</span><span class="sxs-lookup"><span data-stu-id="0285c-115">In the **Open Project** dialog box, open the folder that holds the sample code that you decompressed, and then open the solution (.sln) file for AsyncFineTuningVB.</span></span>  
  
4.  <span data-ttu-id="0285c-116">İçinde **Çözüm Gezgini**, kısayol menüsünü açın **CancelAfterOneTask** proje ve ardından **başlangıç projesi olarak ayarla**.</span><span class="sxs-lookup"><span data-stu-id="0285c-116">In **Solution Explorer**, open the shortcut menu for the **CancelAfterOneTask** project, and then choose **Set as StartUp Project**.</span></span>  
  
5.  <span data-ttu-id="0285c-117">Projeyi çalıştırmak için F5 tuşuna seçin.</span><span class="sxs-lookup"><span data-stu-id="0285c-117">Choose the F5 key to run the project.</span></span>  
  
     <span data-ttu-id="0285c-118">Hata ayıklama olmadan projeyi çalıştırmak için Ctrl + F5 anahtarları'i seçin.</span><span class="sxs-lookup"><span data-stu-id="0285c-118">Choose the Ctrl+F5 keys to run the project without debugging it.</span></span>  
  
6.  <span data-ttu-id="0285c-119">Programı farklı yüklemeler ilk son doğrulamak için birkaç kez çalıştırın.</span><span class="sxs-lookup"><span data-stu-id="0285c-119">Run the program several times to verify that different downloads finish first.</span></span>  
  
 <span data-ttu-id="0285c-120">Projenizi indirin istemiyorsanız, bu konunun sonundaki MainWindow.xaml.vb dosyasını gözden geçirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="0285c-120">If you don't want to download the project, you can review the MainWindow.xaml.vb file at the end of this topic.</span></span>  
  
## <a name="building-the-example"></a><span data-ttu-id="0285c-121">Örnek oluşturma</span><span class="sxs-lookup"><span data-stu-id="0285c-121">Building the Example</span></span>  
 <span data-ttu-id="0285c-122">Bu konudaki örnek da geliştirilmiş projesine ekler [bir zaman uyumsuz görev veya bir liste görevleri iptal etme](http://msdn.microsoft.com/library/d6e4e801-df64-4705-98fc-df725a577fb0) görev listesini iptal etme.</span><span class="sxs-lookup"><span data-stu-id="0285c-122">The example in this topic adds to the project that's developed in [Cancel an Async Task or a List of Tasks](http://msdn.microsoft.com/library/d6e4e801-df64-4705-98fc-df725a577fb0) to cancel a list of tasks.</span></span> <span data-ttu-id="0285c-123">Örnek olsa da, aynı kullanıcı arabirimini kullanır **iptal** düğmesi değil kullanılan açıkça.</span><span class="sxs-lookup"><span data-stu-id="0285c-123">The example uses the same UI, although the **Cancel** button isn’t used explicitly.</span></span>  
  
 <span data-ttu-id="0285c-124">Örnek oluşturmak için kendiniz, adım adım "örnek indirme" bölümündeki yönergeleri izleyin, ancak seçin **CancelAListOfTasks** olarak **başlangıç projesi**.</span><span class="sxs-lookup"><span data-stu-id="0285c-124">To build the example yourself, step by step, follow the instructions in the "Downloading the Example" section, but choose **CancelAListOfTasks** as the **StartUp Project**.</span></span> <span data-ttu-id="0285c-125">Değişiklikleri bu konuda bu projeye ekleyin.</span><span class="sxs-lookup"><span data-stu-id="0285c-125">Add the changes in this topic to that project.</span></span>  
  
 <span data-ttu-id="0285c-126">MainWindow.xaml.vb dosyasındaki **CancelAListOfTasks** proje, her Web sitesi için işlem adımları döngüde taşıma tarafından geçiş başlatma `AccessTheWebAsync` aşağıdaki async yöntemi için.</span><span class="sxs-lookup"><span data-stu-id="0285c-126">In the MainWindow.xaml.vb file of the **CancelAListOfTasks** project, start the transition by moving the processing steps for each website from the loop in `AccessTheWebAsync` to the following async method.</span></span>  
  
```vb  
' ***Bundle the processing steps for a website into one async method.  
Async Function ProcessURLAsync(url As String, client As HttpClient, ct As CancellationToken) As Task(Of Integer)  
  
    ' GetAsync returns a Task(Of HttpResponseMessage).   
    Dim response As HttpResponseMessage = Await client.GetAsync(url, ct)  
  
    ' Retrieve the website contents from the HttpResponseMessage.  
    Dim urlContents As Byte() = Await response.Content.ReadAsByteArrayAsync()  
  
    Return urlContents.Length  
End Function  
```  
  
 <span data-ttu-id="0285c-127">İçinde `AccessTheWebAsync`, bu örnek bir sorgu kullanır <xref:System.Linq.Enumerable.ToArray%2A> yöntemi ve `WhenAny` oluşturma ve görev dizisi başlatma yöntemi.</span><span class="sxs-lookup"><span data-stu-id="0285c-127">In `AccessTheWebAsync`, this example uses a query, the  <xref:System.Linq.Enumerable.ToArray%2A> method, and the `WhenAny` method to create and start an array of tasks.</span></span> <span data-ttu-id="0285c-128">Uygulamayı `WhenAny` dizisi için tek bir görev, beklemenin zaman döndürür görev dizisindeki tamamlanmasından ulaşmak için ilk görev değerlendirir.</span><span class="sxs-lookup"><span data-stu-id="0285c-128">The application of `WhenAny` to the array returns a single task that, when awaited, evaluates to the first task to reach completion in the array of tasks.</span></span>  
  
 <span data-ttu-id="0285c-129">Aşağıdaki değişiklikleri yapın `AccessTheWebAsync`.</span><span class="sxs-lookup"><span data-stu-id="0285c-129">Make the following changes in `AccessTheWebAsync`.</span></span> <span data-ttu-id="0285c-130">Yıldız işareti kod dosyasındaki değişiklikleri işaretleyin.</span><span class="sxs-lookup"><span data-stu-id="0285c-130">Asterisks mark the changes in the code file.</span></span>  
  
1.  <span data-ttu-id="0285c-131">Out yorum yapmak veya döngü silin.</span><span class="sxs-lookup"><span data-stu-id="0285c-131">Comment out or delete the loop.</span></span>  
  
2.  <span data-ttu-id="0285c-132">Bir sorgu, yürütülen oluşturduğunuzda genel görevleri koleksiyonu oluşturur.</span><span class="sxs-lookup"><span data-stu-id="0285c-132">Create a query that, when executed, produces a collection of generic tasks.</span></span> <span data-ttu-id="0285c-133">Her çağrı `ProcessURLAsync` döndüren bir <xref:System.Threading.Tasks.Task%601> burada `TResult` bir tamsayıdır.</span><span class="sxs-lookup"><span data-stu-id="0285c-133">Each call to `ProcessURLAsync` returns a <xref:System.Threading.Tasks.Task%601> where `TResult` is an integer.</span></span>  
  
    ```vb  
    ' ***Create a query that, when executed, returns a collection of tasks.  
    Dim downloadTasksQuery As IEnumerable(Of Task(Of Integer)) =  
        From url In urlList Select ProcessURLAsync(url, client, ct)  
    ```  
  
3.  <span data-ttu-id="0285c-134">Çağrı `ToArray` sorguyu yürütmek ve görevleri başlatın.</span><span class="sxs-lookup"><span data-stu-id="0285c-134">Call `ToArray` to execute the query and start the tasks.</span></span> <span data-ttu-id="0285c-135">Uygulamayı `WhenAny` yöntemi bir sonraki adımda ve sorguyu yürütmek kullanmadan görevlerini başlatmak `ToArray`, ancak diğer yöntemleri görünmeyebilir.</span><span class="sxs-lookup"><span data-stu-id="0285c-135">The application of the `WhenAny` method in the next step would execute the query and start the tasks without using `ToArray`, but other methods might not.</span></span> <span data-ttu-id="0285c-136">Sorgunun yürütülmesi, açıkça zorlamak için en güvenli yöntemdir bakın.</span><span class="sxs-lookup"><span data-stu-id="0285c-136">The safest practice is to force execution of the query explicitly.</span></span>  
  
    ```vb  
    ' ***Use ToArray to execute the query and start the download tasks.   
    Dim downloadTasks As Task(Of Integer)() = downloadTasksQuery.ToArray()  
    ```  
  
4.  <span data-ttu-id="0285c-137">Çağrı `WhenAny` görevleri koleksiyonu.</span><span class="sxs-lookup"><span data-stu-id="0285c-137">Call `WhenAny` on the collection of tasks.</span></span> <span data-ttu-id="0285c-138">`WhenAny`döndüren bir `Task(Of Task(Of Integer))` veya `Task<Task<int>>`.</span><span class="sxs-lookup"><span data-stu-id="0285c-138">`WhenAny` returns a `Task(Of Task(Of Integer))` or `Task<Task<int>>`.</span></span>  <span data-ttu-id="0285c-139">Diğer bir deyişle, `WhenAny` tek bir değerlendiren bir görev döndürür `Task(Of Integer)` veya `Task<int>` zaman beklemenin.</span><span class="sxs-lookup"><span data-stu-id="0285c-139">That is, `WhenAny` returns a task that evaluates to a single `Task(Of Integer)` or `Task<int>` when it’s awaited.</span></span> <span data-ttu-id="0285c-140">Bu tek ilk görevi tamamlamak için koleksiyondaki bir görevdir.</span><span class="sxs-lookup"><span data-stu-id="0285c-140">That single task is the first task in the collection to finish.</span></span> <span data-ttu-id="0285c-141">İlk tamamlandı görev atandığı `firstFinishedTask`.</span><span class="sxs-lookup"><span data-stu-id="0285c-141">The task that finished first is assigned to `firstFinishedTask`.</span></span> <span data-ttu-id="0285c-142">Türü `firstFinishedTask` olan <xref:System.Threading.Tasks.Task%601> nerede `TResult` , dönüş türü tamsayı olmadığından `ProcessURLAsync`.</span><span class="sxs-lookup"><span data-stu-id="0285c-142">The type of `firstFinishedTask` is <xref:System.Threading.Tasks.Task%601> where `TResult` is an integer because that's the return type of `ProcessURLAsync`.</span></span>  
  
```vb  
' ***Call WhenAny and then await the result. The task that finishes   
' first is assigned to firstFinishedTask.  
Dim firstFinishedTask As Task(Of Integer) = Await Task.WhenAny(downloadTasks)  
```  
  
5.  <span data-ttu-id="0285c-143">Bu örnekte, yalnızca ilk bittikten görevdeki ilgilendiğiniz.</span><span class="sxs-lookup"><span data-stu-id="0285c-143">In this example, you’re interested only in the task that finishes first.</span></span> <span data-ttu-id="0285c-144">Bu nedenle kullanmak <xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=nameWithType> kalan görevleri iptal etmek için.</span><span class="sxs-lookup"><span data-stu-id="0285c-144">Therefore, use <xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=nameWithType> to cancel the remaining tasks.</span></span>  
  
```vb  
' ***Cancel the rest of the downloads. You just want the first one.  
cts.Cancel()  
```  
  
6.  <span data-ttu-id="0285c-145">Son olarak, await `firstFinishedTask` indirilen içerik uzunluğu alınamadı.</span><span class="sxs-lookup"><span data-stu-id="0285c-145">Finally, await `firstFinishedTask` to retrieve the length of the downloaded content.</span></span>  
  
```vb  
Dim length = Await firstFinishedTask  
resultsTextBox.Text &= String.Format(vbCrLf & "Length of the downloaded website:  {0}" & vbCrLf, length)  
```  
  
 <span data-ttu-id="0285c-146">Programı farklı yüklemeler ilk son doğrulamak için birkaç kez çalıştırın.</span><span class="sxs-lookup"><span data-stu-id="0285c-146">Run the program several times to verify that different downloads finish first.</span></span>  
  
## <a name="complete-example"></a><span data-ttu-id="0285c-147">Tam Örnek</span><span class="sxs-lookup"><span data-stu-id="0285c-147">Complete Example</span></span>  
 <span data-ttu-id="0285c-148">Aşağıdaki kod örneği için tam MainWindow.xaml.vb veya MainWindow.xaml.cs dosyasıdır.</span><span class="sxs-lookup"><span data-stu-id="0285c-148">The following code is the complete MainWindow.xaml.vb or MainWindow.xaml.cs file for the example.</span></span> <span data-ttu-id="0285c-149">Yıldız işareti, bu örnek için eklenen öğeleri işaretleyin.</span><span class="sxs-lookup"><span data-stu-id="0285c-149">Asterisks mark the elements that were added for this example.</span></span>  
  
 <span data-ttu-id="0285c-150">İçin bir başvuru eklemeniz gerekir fark <xref:System.Net.Http>.</span><span class="sxs-lookup"><span data-stu-id="0285c-150">Notice that you must add a reference for <xref:System.Net.Http>.</span></span>  
  
 <span data-ttu-id="0285c-151">Projeden indirebilirsiniz [zaman uyumsuz örnek: ince ayar uygulamanız](http://go.microsoft.com/fwlink/?LinkId=255046).</span><span class="sxs-lookup"><span data-stu-id="0285c-151">You can download the project from [Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046).</span></span>  
  
```vb  
' Add an Imports directive and a reference for System.Net.Http.  
Imports System.Net.Http  
  
' Add the following Imports directive for System.Threading.  
Imports System.Threading  
  
Class MainWindow  
  
    ' Declare a System.Threading.CancellationTokenSource.  
    Dim cts As CancellationTokenSource  
  
    Private Async Sub startButton_Click(sender As Object, e As RoutedEventArgs)  
  
        ' Instantiate the CancellationTokenSource.  
        cts = New CancellationTokenSource()  
  
        resultsTextBox.Clear()  
  
        Try  
            Await AccessTheWebAsync(cts.Token)  
            resultsTextBox.Text &= vbCrLf & "Download complete."  
  
        Catch ex As OperationCanceledException  
            resultsTextBox.Text &= vbCrLf & "Download canceled." & vbCrLf  
  
        Catch ex As Exception  
            resultsTextBox.Text &= vbCrLf & "Download failed." & vbCrLf  
        End Try  
  
        ' Set the CancellationTokenSource to Nothing when the download is complete.  
        cts = Nothing  
    End Sub  
  
    ' You can still include a Cancel button if you want to.  
    Private Sub cancelButton_Click(sender As Object, e As RoutedEventArgs)  
  
        If cts IsNot Nothing Then  
            cts.Cancel()  
        End If  
    End Sub  
  
    ' Provide a parameter for the CancellationToken.  
    ' Change the return type to Task because the method has no return statement.  
    Async Function AccessTheWebAsync(ct As CancellationToken) As Task  
  
        Dim client As HttpClient = New HttpClient()  
  
        ' Call SetUpURLList to make a list of web addresses.  
        Dim urlList As List(Of String) = SetUpURLList()  
  
        '' Comment out or delete the loop.  
        ''For Each url In urlList  
        ''    ' GetAsync returns a Task(Of HttpResponseMessage).   
        ''    ' Argument ct carries the message if the Cancel button is chosen.   
        ''    ' Note that the Cancel button can cancel all remaining downloads.  
        ''    Dim response As HttpResponseMessage = Await client.GetAsync(url, ct)  
  
        ''    ' Retrieve the website contents from the HttpResponseMessage.  
        ''    Dim urlContents As Byte() = Await response.Content.ReadAsByteArrayAsync()  
  
        ''    resultsTextBox.Text &=  
        ''        String.Format(vbCrLf & "Length of the downloaded string: {0}." & vbCrLf, urlContents.Length)  
        ''Next  
  
        ' ***Create a query that, when executed, returns a collection of tasks.  
        Dim downloadTasksQuery As IEnumerable(Of Task(Of Integer)) =  
            From url In urlList Select ProcessURLAsync(url, client, ct)  
  
        ' ***Use ToArray to execute the query and start the download tasks.   
        Dim downloadTasks As Task(Of Integer)() = downloadTasksQuery.ToArray()  
  
        ' ***Call WhenAny and then await the result. The task that finishes   
        ' first is assigned to firstFinishedTask.  
        Dim firstFinishedTask As Task(Of Integer) = Await Task.WhenAny(downloadTasks)  
  
        ' ***Cancel the rest of the downloads. You just want the first one.  
        cts.Cancel()  
  
        ' ***Await the first completed task and display the results  
        ' Run the program several times to demonstrate that different  
        ' websites can finish first.  
        Dim length = Await firstFinishedTask  
        resultsTextBox.Text &= String.Format(vbCrLf & "Length of the downloaded website:  {0}" & vbCrLf, length)  
    End Function  
  
    ' ***Bundle the processing steps for a website into one async method.  
    Async Function ProcessURLAsync(url As String, client As HttpClient, ct As CancellationToken) As Task(Of Integer)  
  
        ' GetAsync returns a Task(Of HttpResponseMessage).   
        Dim response As HttpResponseMessage = Await client.GetAsync(url, ct)  
  
        ' Retrieve the website contents from the HttpResponseMessage.  
        Dim urlContents As Byte() = Await response.Content.ReadAsByteArrayAsync()  
  
        Return urlContents.Length  
    End Function  
  
    ' Add a method that creates a list of web addresses.  
    Private Function SetUpURLList() As List(Of String)  
  
        Dim urls = New List(Of String) From  
            {  
                "http://msdn.microsoft.com",  
                "http://msdn.microsoft.com/library/hh290138.aspx",  
                "http://msdn.microsoft.com/library/hh290140.aspx",  
                "http://msdn.microsoft.com/library/dd470362.aspx",  
                "http://msdn.microsoft.com/library/aa578028.aspx",  
                "http://msdn.microsoft.com/library/ms404677.aspx",  
                "http://msdn.microsoft.com/library/ff730837.aspx"  
            }  
        Return urls  
    End Function  
  
End Class  
  
' Sample output:  
  
' Length of the downloaded website:  158856  
  
' Download complete.  
```  
  
## <a name="see-also"></a><span data-ttu-id="0285c-152">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="0285c-152">See Also</span></span>  
 <xref:System.Threading.Tasks.Task.WhenAny%2A>  
 [<span data-ttu-id="0285c-153">Async uygulamanızda (Visual Basic) hassas ayar yapma</span><span class="sxs-lookup"><span data-stu-id="0285c-153">Fine-Tuning Your Async Application (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md)  
 [<span data-ttu-id="0285c-154">Zaman uyumsuz programlama ile Async ve Await (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0285c-154">Asynchronous Programming with Async and Await (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/async/index.md)  
 [<span data-ttu-id="0285c-155">Zaman uyumsuz örnek: İnce uygulamanızı ayarlama</span><span class="sxs-lookup"><span data-stu-id="0285c-155">Async Sample: Fine Tuning Your Application</span></span>](http://go.microsoft.com/fwlink/?LinkId=255046)