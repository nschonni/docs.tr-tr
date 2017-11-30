---
title: "Nasıl yapılır: nesne verilerini bir XML dosyasına (C#) yazma"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 7681eb98-703d-4005-a369-26a7bca0f894
caps.latest.revision: "4"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: f43075c0b4d04ff935e7a29ed270b348209d17b1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-write-object-data-to-an-xml-file-c"></a><span data-ttu-id="fe6db-102">Nasıl yapılır: nesne verilerini bir XML dosyasına (C#) yazma</span><span class="sxs-lookup"><span data-stu-id="fe6db-102">How to: Write Object Data to an XML File (C#)</span></span>
<span data-ttu-id="fe6db-103">Bu örnek, bir XML dosyası kullanarak bir sınıftan nesne Yazar <xref:System.Xml.Serialization.XmlSerializer> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="fe6db-103">This example writes the object from a class to an XML file using the <xref:System.Xml.Serialization.XmlSerializer> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fe6db-104">Örnek</span><span class="sxs-lookup"><span data-stu-id="fe6db-104">Example</span></span>  
  
```csharp  
public class XMLWrite  
{  
  
   static void Main(string[] args)  
    {  
        WriteXML();  
    }  
  
    public class Book  
    {  
        public String title;   
    }  
  
    public static void WriteXML()  
    {  
        Book overview = new Book();  
        overview.title = "Serialization Overview";  
        System.Xml.Serialization.XmlSerializer writer =   
            new System.Xml.Serialization.XmlSerializer(typeof(Book));  
  
        var path = Environment.GetFolderPath(Environment.SpecialFolder.MyDocuments) + "//SerializationOverview.xml";  
        System.IO.FileStream file = System.IO.File.Create(path);  
  
        writer.Serialize(file, overview);  
        file.Close();  
    }  
}  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="fe6db-105">Kod Derleniyor</span><span class="sxs-lookup"><span data-stu-id="fe6db-105">Compiling the Code</span></span>  
 <span data-ttu-id="fe6db-106">Sınıf parametresiz ortak bir oluşturucuya sahip olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="fe6db-106">The class must have a public constructor without parameters.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="fe6db-107">Güçlü Programlama</span><span class="sxs-lookup"><span data-stu-id="fe6db-107">Robust Programming</span></span>  
 <span data-ttu-id="fe6db-108">Aşağıdaki koşullar özel bir duruma neden olabilir:</span><span class="sxs-lookup"><span data-stu-id="fe6db-108">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="fe6db-109">Serileştirilen sınıfı genel, parametresiz bir oluşturucu yok.</span><span class="sxs-lookup"><span data-stu-id="fe6db-109">The class being serialized does not have a public, parameterless constructor.</span></span>  
  
-   <span data-ttu-id="fe6db-110">Dosya var ve salt okunurdur (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="fe6db-110">The file exists and is read-only (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="fe6db-111">Yol çok uzun (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="fe6db-111">The path is too long (<xref:System.IO.PathTooLongException>).</span></span>  
  
-   <span data-ttu-id="fe6db-112">Disk dolu olduğundan (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="fe6db-112">The disk is full (<xref:System.IO.IOException>).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="fe6db-113">.NET Framework Güvenliği</span><span class="sxs-lookup"><span data-stu-id="fe6db-113">.NET Framework Security</span></span>  
 <span data-ttu-id="fe6db-114">Bu örnek, dosyanın zaten mevcut değilse yeni bir dosya oluşturur.</span><span class="sxs-lookup"><span data-stu-id="fe6db-114">This example creates a new file, if the file does not already exist.</span></span> <span data-ttu-id="fe6db-115">Bir uygulama bir dosya oluşturmak gerekirse, bu uygulamanın ihtiyacı `Create` klasörü için erişim.</span><span class="sxs-lookup"><span data-stu-id="fe6db-115">If an application needs to create a file, that application needs `Create` access for the folder.</span></span> <span data-ttu-id="fe6db-116">Dosya zaten varsa, uygulamanın yalnızca ihtiyacı `Write` erişimi, daha düşük ayrıcalık.</span><span class="sxs-lookup"><span data-stu-id="fe6db-116">If the file already exists, the application needs only `Write` access, a lesser privilege.</span></span> <span data-ttu-id="fe6db-117">Mümkünse, dağıtım sırasında dosyası oluşturun ve yalnızca izni için daha güvenli olan `Read` tek bir dosyaya erişim yerine `Create` bir klasör için erişim.</span><span class="sxs-lookup"><span data-stu-id="fe6db-117">Where possible, it is more secure to create the file during deployment, and only grant `Read` access to a single file, rather than `Create` access for a folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe6db-118">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="fe6db-118">See Also</span></span>  
 <xref:System.IO.StreamWriter>  
 [<span data-ttu-id="fe6db-119">Nasıl yapılır: nesne verilerini bir XML dosyasından (C#) okuma</span><span class="sxs-lookup"><span data-stu-id="fe6db-119">How to: Read Object Data from an XML File (C#)</span></span>](../../../../csharp/programming-guide/concepts/serialization/how-to-read-object-data-from-an-xml-file.md)  
 [<span data-ttu-id="fe6db-120">Seri hale getirme (C#)</span><span class="sxs-lookup"><span data-stu-id="fe6db-120">Serialization (C# )</span></span>](../../../../csharp/programming-guide/concepts/serialization/index.md)