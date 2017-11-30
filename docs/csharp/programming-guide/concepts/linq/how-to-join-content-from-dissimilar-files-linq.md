---
title: "Nasıl yapılır: (LINQ) (C#) farklı dosyalardan içerik birleştirme"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: aa2d12a6-70a9-492f-a6db-b2b850d46811
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: ac5c9f2037e3254c6262efe00fcbff31664dcd70
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-join-content-from-dissimilar-files-linq-c"></a><span data-ttu-id="b4dff-102">Nasıl yapılır: (LINQ) (C#) farklı dosyalardan içerik birleştirme</span><span class="sxs-lookup"><span data-stu-id="b4dff-102">How to: Join Content from Dissimilar Files (LINQ) (C#)</span></span>
<span data-ttu-id="b4dff-103">Bu örnek, eşleşen bir anahtarı olarak kullanılan bir ortak değer paylaşmak, virgülle ayrılmış iki dosya verileri nasıl gösterir.</span><span class="sxs-lookup"><span data-stu-id="b4dff-103">This example shows how to join data from two comma-delimited files that share a common value that is used as a matching key.</span></span> <span data-ttu-id="b4dff-104">Bu teknik iki elektronik tablolar verileri birleştirmek varsa veya bir elektronik tablo ve dosya yeni bir dosyaya başka bir biçime sahip yararlı olabilir.</span><span class="sxs-lookup"><span data-stu-id="b4dff-104">This technique can be useful if you have to combine data from two spreadsheets, or from a spreadsheet and from a file that has another format, into a new file.</span></span> <span data-ttu-id="b4dff-105">Yapılandırılmış metin herhangi bir tür ile çalışmak için örnek değiştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="b4dff-105">You can modify the example to work with any kind of structured text.</span></span>  
  
### <a name="to-create-the-data-files"></a><span data-ttu-id="b4dff-106">Veri dosyaları oluşturmak için</span><span class="sxs-lookup"><span data-stu-id="b4dff-106">To create the data files</span></span>  
  
1.  <span data-ttu-id="b4dff-107">Aşağıdaki satırları scores.csv adlı bir dosyaya kopyalayın ve proje klasörüne kaydedin.</span><span class="sxs-lookup"><span data-stu-id="b4dff-107">Copy the following lines into a file that is named scores.csv and save it to your project folder.</span></span> <span data-ttu-id="b4dff-108">Dosya, elektronik tablo verilerini temsil eder.</span><span class="sxs-lookup"><span data-stu-id="b4dff-108">The file represents spreadsheet data.</span></span> <span data-ttu-id="b4dff-109">Sütun 1 öğrencinin kimliği olduğunu ve sütun 2'den 5 test puanları.</span><span class="sxs-lookup"><span data-stu-id="b4dff-109">Column 1 is the student's ID, and columns 2 through 5 are test scores.</span></span>  
  
    ```  
    111, 97, 92, 81, 60  
    112, 75, 84, 91, 39  
    113, 88, 94, 65, 91  
    114, 97, 89, 85, 82  
    115, 35, 72, 91, 70  
    116, 99, 86, 90, 94  
    117, 93, 92, 80, 87  
    118, 92, 90, 83, 78  
    119, 68, 79, 88, 92  
    120, 99, 82, 81, 79  
    121, 96, 85, 91, 60  
    122, 94, 92, 91, 91  
    ```  
  
2.  <span data-ttu-id="b4dff-110">Aşağıdaki satırları names.csv adlı bir dosyaya kopyalayın ve proje klasörüne kaydedin.</span><span class="sxs-lookup"><span data-stu-id="b4dff-110">Copy the following lines into a file that is named names.csv and save it to your project folder.</span></span> <span data-ttu-id="b4dff-111">Öğrencinin Soyadı, ad ve Öğrenci Kimliği içeren bir elektronik tablo dosyayı temsil eder</span><span class="sxs-lookup"><span data-stu-id="b4dff-111">The file represents a spreadsheet that contains the student's last name, first name, and student ID.</span></span>  
  
    ```  
    Omelchenko,Svetlana,111  
    O'Donnell,Claire,112  
    Mortensen,Sven,113  
    Garcia,Cesar,114  
    Garcia,Debra,115  
    Fakhouri,Fadi,116  
    Feng,Hanying,117  
    Garcia,Hugo,118  
    Tucker,Lance,119  
    Adams,Terry,120  
    Zabokritski,Eugene,121  
    Tucker,Michael,122  
    ```  
  
## <a name="example"></a><span data-ttu-id="b4dff-112">Örnek</span><span class="sxs-lookup"><span data-stu-id="b4dff-112">Example</span></span>  
  
```csharp  
class JoinStrings  
{  
    static void Main()  
    {  
        // Join content from dissimilar files that contain  
        // related information. File names.csv contains the student  
        // name plus an ID number. File scores.csv contains the ID   
        // and a set of four test scores. The following query joins  
        // the scores to the student names by using ID as a  
        // matching key.  
  
        string[] names = System.IO.File.ReadAllLines(@"../../../names.csv");  
        string[] scores = System.IO.File.ReadAllLines(@"../../../scores.csv");  
  
        // Name:    Last[0],       First[1],  ID[2]  
        //          Omelchenko,    Svetlana,  11  
        // Score:   StudentID[0],  Exam1[1]   Exam2[2],  Exam3[3],  Exam4[4]  
        //          111,           97,        92,        81,        60  
  
        // This query joins two dissimilar spreadsheets based on common ID value.  
        // Multiple from clauses are used instead of a join clause  
        // in order to store results of id.Split.  
        IEnumerable<string> scoreQuery1 =  
            from name in names  
            let nameFields = name.Split(',')  
            from id in scores  
            let scoreFields = id.Split(',')  
            where nameFields[2] == scoreFields[0]  
            select nameFields[0] + "," + scoreFields[1] + "," + scoreFields[2]   
                   + "," + scoreFields[3] + "," + scoreFields[4];  
  
        // Pass a query variable to a method and execute it  
        // in the method. The query itself is unchanged.  
        OutputQueryResults(scoreQuery1, "Merge two spreadsheets:");  
  
        // Keep console window open in debug mode.  
        Console.WriteLine("Press any key to exit");  
        Console.ReadKey();  
    }  
  
    static void OutputQueryResults(IEnumerable<string> query, string message)  
    {  
        Console.WriteLine(System.Environment.NewLine + message);  
        foreach (string item in query)  
        {  
            Console.WriteLine(item);  
        }  
        Console.WriteLine("{0} total names in list", query.Count());  
    }  
}  
/* Output:  
Merge two spreadsheets:  
Adams, 99, 82, 81, 79  
Fakhouri, 99, 86, 90, 94  
Feng, 93, 92, 80, 87  
Garcia, 97, 89, 85, 82  
Garcia, 35, 72, 91, 70  
Garcia, 92, 90, 83, 78  
Mortensen, 88, 94, 65, 91  
O'Donnell, 75, 84, 91, 39  
Omelchenko, 97, 92, 81, 60  
Tucker, 68, 79, 88, 92  
Tucker, 94, 92, 91, 91  
Zabokritski, 96, 85, 91, 60  
12 total names in list  
 */  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b4dff-113">Kod Derleniyor</span><span class="sxs-lookup"><span data-stu-id="b4dff-113">Compiling the Code</span></span>  
 <span data-ttu-id="b4dff-114">.NET Framework sürüm 3.5 veya daha yüksek System.Core.dll başvuru hedefleyen bir proje oluşturun ve `using` System.Linq ve System.IO ad alanları için yönergeleri.</span><span class="sxs-lookup"><span data-stu-id="b4dff-114">Create a project that targets the .NET Framework  version 3.5 or higher, with a reference to System.Core.dll and `using` directives for the System.Linq and System.IO namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4dff-115">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="b4dff-115">See Also</span></span>  
 [<span data-ttu-id="b4dff-116">LINQ ve dizeler (C#)</span><span class="sxs-lookup"><span data-stu-id="b4dff-116">LINQ and Strings (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-and-strings.md)  
 [<span data-ttu-id="b4dff-117">LINQ ve dosya dizinleri (C#)</span><span class="sxs-lookup"><span data-stu-id="b4dff-117">LINQ and File Directories (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-and-file-directories.md)