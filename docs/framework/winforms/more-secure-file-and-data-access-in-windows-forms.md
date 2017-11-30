---
title: "Windows Forms'ta Daha Güvenli Dosya ve Veri Erişimi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security [Windows Forms], file access
- registry [Windows Forms]
- data access [Windows Forms]
- database access (Windows Forms security)
- data [Windows Forms], secure access
- file access [Windows Forms]
- security [Windows Forms], data access
ms.assetid: 3cd3e55b-2f5e-40dd-835d-f50f7ce08967
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f447df16aab29b91da6f34b8afd812dea2d109ef
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="more-secure-file-and-data-access-in-windows-forms"></a><span data-ttu-id="ac82f-102">Windows Forms'ta Daha Güvenli Dosya ve Veri Erişimi</span><span class="sxs-lookup"><span data-stu-id="ac82f-102">More Secure File and Data Access in Windows Forms</span></span>
<span data-ttu-id="ac82f-103">[!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] İzinlerini kaynakları ve veri korumaya yardımcı olmak için kullanır.</span><span class="sxs-lookup"><span data-stu-id="ac82f-103">The [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] uses permissions to help protect resources and data.</span></span> <span data-ttu-id="ac82f-104">Burada, uygulamanızın Okuma veya yazma veri uygulamaya verilen izinler bağlıdır.</span><span class="sxs-lookup"><span data-stu-id="ac82f-104">Where your application can read or write data depends on the permissions granted to the application.</span></span> <span data-ttu-id="ac82f-105">Uygulamanızı bir kısmi güven ortamında çalıştığında, verilerinize erişimi olmayabilir veya verilere erişme şeklini değiştirmek zorunda kalabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="ac82f-105">When your application runs in a partial trust environment, you might not have access to your data or you might have to change the way you access the data.</span></span>  
  
 <span data-ttu-id="ac82f-106">Bir güvenlik kısıtlama karşılaştığınızda, iki seçeneğiniz vardır: (Bu verildiğini uygulamanıza varsayılarak) izni assert veya kısmi güvende çalışması için yazılmış özelliği sürümünü kullanın.</span><span class="sxs-lookup"><span data-stu-id="ac82f-106">When you encounter a security restriction, you have two options: assert the permission (assuming it has been granted to your application), or use a version of the feature written to work in partial trust.</span></span> <span data-ttu-id="ac82f-107">Aşağıdaki bölümlerde dosya, veritabanı ve kayıt defteri erişimi bir kısmi güven ortamında çalışan uygulamalardan ile çalışma konusunda açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="ac82f-107">The following sections discuss how to work with file, database, and registry access from applications that are running in a partial trust environment.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ac82f-108">Varsayılan olarak, oluşturma araçları [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] dağıtımları varsayılan bu dağıtımlar isteyen tam güven için çalıştıkları bilgisayarlardan.</span><span class="sxs-lookup"><span data-stu-id="ac82f-108">By default, tools that generate [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] deployments default these deployments to requesting Full Trust from the computers on which they run.</span></span> <span data-ttu-id="ac82f-109">Kısmi güvende çalıştırma ek güvenlik avantajları istemediğinize karar verirseniz, bu varsayılan olarak ya da değiştirmeniz gerekir [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] veya biri [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] Araçları (Mage.exe veya MageUI.exe).</span><span class="sxs-lookup"><span data-stu-id="ac82f-109">If you decide you want the added security benefits of running in partial trust, you must change this default in either [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] or one of the [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] tools (Mage.exe or MageUI.exe).</span></span> <span data-ttu-id="ac82f-110">Windows Forms güvenliği hakkında ve uygulamanız için uygun güven düzeyini belirleme hakkında daha fazla bilgi için bkz: [Windows Forms'a genel bakış güvenlik](../../../docs/framework/winforms/security-in-windows-forms-overview.md).</span><span class="sxs-lookup"><span data-stu-id="ac82f-110">For more information about Windows Forms security, and on how to determine the appropriate trust level for your application, see [Security in Windows Forms Overview](../../../docs/framework/winforms/security-in-windows-forms-overview.md).</span></span>  
  
## <a name="file-access"></a><span data-ttu-id="ac82f-111">Dosya erişimi</span><span class="sxs-lookup"><span data-stu-id="ac82f-111">File Access</span></span>  
 <span data-ttu-id="ac82f-112"><xref:System.Security.Permissions.FileIOPermission> Sınıf denetimleri dosya ve klasör erişim [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ac82f-112">The <xref:System.Security.Permissions.FileIOPermission> class controls file and folder access in the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="ac82f-113">Varsayılan olarak, güvenlik sistemi değil vermez <xref:System.Security.Permissions.FileIOPermission> kısmi güven ortamlara yerel intranet ve Internet bölgeleri gibi.</span><span class="sxs-lookup"><span data-stu-id="ac82f-113">By default, the security system does not grant the <xref:System.Security.Permissions.FileIOPermission> to partial trust environments such as the local intranet and Internet zones.</span></span> <span data-ttu-id="ac82f-114">Ancak, uygulamanızın tasarımını ya da dosyalara erişim için farklı yöntemler kullanın dosya erişimi gerektiren bir uygulama bu ortamlarda hala çalışabilir.</span><span class="sxs-lookup"><span data-stu-id="ac82f-114">However, an application that requires file access can still function in these environments if you modify the design of your application or use different methods to access files.</span></span> <span data-ttu-id="ac82f-115">Varsayılan olarak, yerel intranet bölgesine aynı site erişimi ve aynı dizin erişimi, geri, kaynak siteye bağlanmak ve kendi yükleme dizininden okumak için sahip hakkı verilir.</span><span class="sxs-lookup"><span data-stu-id="ac82f-115">By default, the local intranet zone is granted the right to have same site access and same directory access, to connect back to the site of its origin, and to read from its installation directory.</span></span> <span data-ttu-id="ac82f-116">Varsayılan olarak, Internet bölgesi yalnızca verilir kendi başlangıç sitesine geri bağlanma hakkı.</span><span class="sxs-lookup"><span data-stu-id="ac82f-116">By default, the Internet zone, is only granted the right to connect back to the site of its origin.</span></span>  
  
### <a name="user-specified-files"></a><span data-ttu-id="ac82f-117">Kullanıcı tarafından belirtilen dosyaları</span><span class="sxs-lookup"><span data-stu-id="ac82f-117">User-Specified Files</span></span>  
 <span data-ttu-id="ac82f-118">Dağıtılacak bir yolu dosya erişimi olmaması ile izin kullanarak belirli dosya bilgilerini sağlamak için kullanıcıdan istemek için şu <xref:System.Windows.Forms.OpenFileDialog> veya <xref:System.Windows.Forms.SaveFileDialog> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="ac82f-118">One way to deal with not having file access permission is to prompt the user to provide specific file information by using the <xref:System.Windows.Forms.OpenFileDialog> or <xref:System.Windows.Forms.SaveFileDialog> class.</span></span> <span data-ttu-id="ac82f-119">Bu kullanıcı etkileşimi uygulama kötü amaçlı olarak özel dosyaları yükleyemedi veya önemli dosyaların üzerine yazıp, bazı güvence sağlar, yardımcı olur.</span><span class="sxs-lookup"><span data-stu-id="ac82f-119">This user interaction helps provide some assurance that the application cannot maliciously load private files or overwrite important files.</span></span> <span data-ttu-id="ac82f-120"><xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> Ve <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> okuma ve yazma dosya erişimi kullanıcı tarafından belirtilen dosya için dosya akışı açarak yöntemleri sağlar.</span><span class="sxs-lookup"><span data-stu-id="ac82f-120">The <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> and <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> methods provide read and write file access by opening the file stream for the file that the user specified.</span></span> <span data-ttu-id="ac82f-121">Yöntemleri'de dosyanın yolu anlaşılması güç kullanıcının dosyayı koruyun.</span><span class="sxs-lookup"><span data-stu-id="ac82f-121">The methods also help protect the user's file by obscuring the file's path.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ac82f-122">Bu izinleri uygulamanızı Internet bölgesi ya da Intranet bölgesi olmasına bağlı olarak değişir.</span><span class="sxs-lookup"><span data-stu-id="ac82f-122">These permissions differ depending on whether your application is in the Internet zone or Intranet zone.</span></span> <span data-ttu-id="ac82f-123">Internet bölgesi uygulamalarına yalnızca kullanabilir <xref:System.Windows.Forms.OpenFileDialog>, Intranet uygulamalarını dosya iletişim izni sınırsız vardır ancak.</span><span class="sxs-lookup"><span data-stu-id="ac82f-123">Internet zone applications can only use the <xref:System.Windows.Forms.OpenFileDialog>, whereas Intranet applications have unrestricted file dialog permission.</span></span>  
  
 <span data-ttu-id="ac82f-124"><xref:System.Security.Permissions.FileDialogPermission> Sınıfını belirtir ne tür bir dosya iletişim kutusu, uygulamanızın kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="ac82f-124">The <xref:System.Security.Permissions.FileDialogPermission> class specifies what type of file dialog box your application can use.</span></span> <span data-ttu-id="ac82f-125">Aşağıdaki tabloda, her kullanılacak olmalıdır değeri gösterilmektedir <xref:System.Windows.Forms.FileDialog> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="ac82f-125">The following table shows the value you must have to use each <xref:System.Windows.Forms.FileDialog> class.</span></span>  
  
|<span data-ttu-id="ac82f-126">örneği</span><span class="sxs-lookup"><span data-stu-id="ac82f-126">Class</span></span>|<span data-ttu-id="ac82f-127">Gerekli erişim değeri</span><span class="sxs-lookup"><span data-stu-id="ac82f-127">Required access value</span></span>|  
|-----------|---------------------------|  
|<xref:System.Windows.Forms.OpenFileDialog>|<xref:System.Security.Permissions.FileDialogPermissionAccess.Open>|  
|<xref:System.Windows.Forms.SaveFileDialog>|<xref:System.Security.Permissions.FileDialogPermissionAccess.Save>|  
  
> [!NOTE]
>  <span data-ttu-id="ac82f-128">Belirli bir izin kadar istenen değil <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> yöntemi gerçekte çağrılır.</span><span class="sxs-lookup"><span data-stu-id="ac82f-128">The specific permission is not requested until the <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> method is actually called.</span></span>  
  
 <span data-ttu-id="ac82f-129">Dosya iletişim kutusu görüntülemek için izni tüm üyeleri için uygulama tam erişim vermez <xref:System.Windows.Forms.FileDialog>, <xref:System.Windows.Forms.OpenFileDialog>, ve <xref:System.Windows.Forms.SaveFileDialog> sınıfları.</span><span class="sxs-lookup"><span data-stu-id="ac82f-129">Permission to display a file dialog box does not grant your application full access to all members of the <xref:System.Windows.Forms.FileDialog>, <xref:System.Windows.Forms.OpenFileDialog>, and <xref:System.Windows.Forms.SaveFileDialog> classes.</span></span> <span data-ttu-id="ac82f-130">Her yöntemini çağırmak için gerekli izinleri tam görmek için bu yöntem için başvuru konusunun [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] sınıf kitaplığı belgeleri.</span><span class="sxs-lookup"><span data-stu-id="ac82f-130">For the exact permissions that are required to call each method, see the reference topic for that method in the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] class library documentation.</span></span>  
  
 <span data-ttu-id="ac82f-131">Aşağıdaki kod örneğinde <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> yöntemi bir kullanıcı tarafından belirtilen dosyaya açmak için bir <xref:System.Windows.Forms.RichTextBox> denetim.</span><span class="sxs-lookup"><span data-stu-id="ac82f-131">The following code example uses the <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> method to open a user-specified file into a <xref:System.Windows.Forms.RichTextBox> control.</span></span> <span data-ttu-id="ac82f-132">Örnek gerektirir <xref:System.Security.Permissions.FileDialogPermission> ve ilişkili <xref:System.Security.Permissions.FileDialogPermissionAttribute.Open%2A> numaralandırma değeri.</span><span class="sxs-lookup"><span data-stu-id="ac82f-132">The example requires <xref:System.Security.Permissions.FileDialogPermission> and the associated <xref:System.Security.Permissions.FileDialogPermissionAttribute.Open%2A> enumeration value.</span></span> <span data-ttu-id="ac82f-133">Bu örnek nasıl işleneceğini gösterir <xref:System.Security.SecurityException> belirlemek için olup olmadığını kaydetme özelliğini devre dışı bırakılmalıdır.</span><span class="sxs-lookup"><span data-stu-id="ac82f-133">The example demonstrates how to handle the <xref:System.Security.SecurityException> to determine whether the save feature should be disabled.</span></span> <span data-ttu-id="ac82f-134">Bu örnek gerektiren, <xref:System.Windows.Forms.Form> sahip bir <xref:System.Windows.Forms.Button> adlı Denetim `ButtonOpen`ve bir <xref:System.Windows.Forms.RichTextBox> adlı Denetim `RtfBoxMain`.</span><span class="sxs-lookup"><span data-stu-id="ac82f-134">This example requires that your <xref:System.Windows.Forms.Form> has a <xref:System.Windows.Forms.Button> control named `ButtonOpen`, and a <xref:System.Windows.Forms.RichTextBox> control named `RtfBoxMain`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ac82f-135">Programlama mantığı için Kaydet özelliği örnekte gösterilmez.</span><span class="sxs-lookup"><span data-stu-id="ac82f-135">The programming logic for the save feature is not shown in the example.</span></span>  
  
```vb  
Private Sub ButtonOpen_Click(ByVal sender As System.Object, _  
    ByVal e As System.EventArgs) Handles ButtonOpen.Click   
  
    Dim editingFileName as String = ""  
    Dim saveAllowed As Boolean = True  
  
    ' Displays the OpenFileDialog.  
    If (OpenFileDialog1.ShowDialog() = DialogResult.OK) Then  
        Dim userStream as System.IO.Stream  
        Try   
            ' Opens the file stream for the file selected by the user.  
            userStream =OpenFileDialog1.OpenFile()   
            Me.RtfBoxMain.LoadFile(userStream, _  
                RichTextBoxStreamType.PlainText)  
        Finally  
            userStream.Close()  
        End Try  
  
        ' Tries to get the file name selected by the user.  
        ' Failure means that the application does not have  
        ' unrestricted permission to the file.  
        Try   
            editingFileName = OpenFileDialog1.FileName  
        Catch ex As Exception  
            If TypeOf ex Is System.Security.SecurityException Then   
                ' The application does not have unrestricted permission   
                ' to the file so the save feature will be disabled.  
                saveAllowed = False   
            Else   
                Throw ex  
            End If  
        End Try  
    End If  
End Sub  
```  
  
```csharp  
private void ButtonOpen_Click(object sender, System.EventArgs e)   
{  
    String editingFileName = "";  
    Boolean saveAllowed = true;  
  
    // Displays the OpenFileDialog.  
    if (openFileDialog1.ShowDialog() == DialogResult.OK)   
    {  
        // Opens the file stream for the file selected by the user.  
        using (System.IO.Stream userStream = openFileDialog1.OpenFile())   
        {  
            this.RtfBoxMain.LoadFile(userStream,  
                RichTextBoxStreamType.PlainText);  
            userStream.Close();  
        }  
  
        // Tries to get the file name selected by the user.  
        // Failure means that the application does not have  
        // unrestricted permission to the file.  
        try   
        {  
            editingFileName = openFileDialog1.FileName;  
        }   
        catch (Exception ex)   
        {  
            if (ex is System.Security.SecurityException)   
            {  
                // The application does not have unrestricted permission   
                // to the file so the save feature will be disabled.  
                saveAllowed = false;   
            }   
            else   
            {  
                throw ex;  
            }  
        }  
    }  
}  
```  
  
> [!NOTE]
>  <span data-ttu-id="ac82f-136">İçinde [!INCLUDE[csprcs](../../../includes/csprcs-md.md)], olay işleyicisi olanak sağlamak için kod ekleme emin olun.</span><span class="sxs-lookup"><span data-stu-id="ac82f-136">In [!INCLUDE[csprcs](../../../includes/csprcs-md.md)], ensure that you add code to enable the event handler.</span></span> <span data-ttu-id="ac82f-137">Aşağıdaki kod, önceki örnek kodu kullanarak, olay işleyicisi etkinleştirme gösterir.`this.ButtonOpen.Click += newSystem.Windows.Forms.EventHandler(this.ButtonOpen_Click);`</span><span class="sxs-lookup"><span data-stu-id="ac82f-137">By using the code from the previous example, the following code shows how to enable the event handler.`this.ButtonOpen.Click += newSystem.Windows.Forms.EventHandler(this.ButtonOpen_Click);`</span></span>  
  
### <a name="other-files"></a><span data-ttu-id="ac82f-138">Diğer dosyaları</span><span class="sxs-lookup"><span data-stu-id="ac82f-138">Other Files</span></span>  
 <span data-ttu-id="ac82f-139">Bazen okumak veya kullanıcı, uygulama ayarları ne zaman sürdürülmesi gereken gibi belirtmediğinden emin dosyaları yazmak gerekir.</span><span class="sxs-lookup"><span data-stu-id="ac82f-139">Sometimes you will need to read or write to files that the user does not specify, such as when you must persist application settings.</span></span> <span data-ttu-id="ac82f-140">Yerel intranet ve Internet bölgeleri uygulamanızı yerel bir dosyaya veri depolamak için izne sahip değil.</span><span class="sxs-lookup"><span data-stu-id="ac82f-140">In the local intranet and Internet zones, your application will not have permission to store data in a local file.</span></span> <span data-ttu-id="ac82f-141">Ancak, uygulamanızın yalıtılmış depolamada verileri depolamak mümkün olacaktır.</span><span class="sxs-lookup"><span data-stu-id="ac82f-141">However, your application will be able to store data in isolated storage.</span></span> <span data-ttu-id="ac82f-142">Yalıtılmış Depolama verilerinin depolandığı gerçek dizin konumları içeren depoları olarak adlandırılan bir veya daha fazla yalıtılmış depolama dosyaları içeren bir soyut veri bölme (belirli bir depolama konumu değil) olur.</span><span class="sxs-lookup"><span data-stu-id="ac82f-142">Isolated storage is an abstract data compartment (not a specific storage location) that contains one or more isolated storage files, called stores, that contain the actual directory locations where data is stored.</span></span> <span data-ttu-id="ac82f-143">Dosya erişim izinleri gibi <xref:System.Security.Permissions.FileIOPermission> gerekli değildir; bunun yerine, <xref:System.Security.Permissions.IsolatedStoragePermission> sınıfı yalıtılmış depolama için izinleri denetler.</span><span class="sxs-lookup"><span data-stu-id="ac82f-143">File access permissions like <xref:System.Security.Permissions.FileIOPermission> are not required; instead, the <xref:System.Security.Permissions.IsolatedStoragePermission> class controls the permissions for isolated storage.</span></span> <span data-ttu-id="ac82f-144">Varsayılan olarak, yerel intranet ve Internet bölgeleri çalışmakta olan uygulamalar yalıtılmış depolama kullanarak veri depolayabilir; Ancak, disk kotası gibi ayarları farklılık gösterebilir.</span><span class="sxs-lookup"><span data-stu-id="ac82f-144">By default, applications that are running in the local intranet and Internet zones can store data using isolated storage; however, settings like disk quota can vary.</span></span> <span data-ttu-id="ac82f-145">Yalıtılmış depolama hakkında daha fazla bilgi için bkz: [yalıtılmış depolama](../../../docs/standard/io/isolated-storage.md).</span><span class="sxs-lookup"><span data-stu-id="ac82f-145">For more information about isolated storage, see [Isolated Storage](../../../docs/standard/io/isolated-storage.md).</span></span>  
  
 <span data-ttu-id="ac82f-146">Aşağıdaki örnek, bir depolama alanında bulunan bir dosyaya veri yazmak için yalıtılmış depolama kullanır.</span><span class="sxs-lookup"><span data-stu-id="ac82f-146">The following example uses isolated storage to write data to a file located in a store.</span></span> <span data-ttu-id="ac82f-147">Örnek gerektirir <xref:System.Security.Permissions.IsolatedStorageFilePermission> ve <xref:System.Security.Permissions.IsolatedStorageContainment.DomainIsolationByUser> numaralandırma değeri.</span><span class="sxs-lookup"><span data-stu-id="ac82f-147">The example requires <xref:System.Security.Permissions.IsolatedStorageFilePermission> and the <xref:System.Security.Permissions.IsolatedStorageContainment.DomainIsolationByUser> enumeration value.</span></span> <span data-ttu-id="ac82f-148">Örnek okuma ve yazma belirli özellik değerlerini gösterir <xref:System.Windows.Forms.Button> yalıtılmış depolama dosyasında denetimine.</span><span class="sxs-lookup"><span data-stu-id="ac82f-148">The example demonstrates reading and writing certain property values of the <xref:System.Windows.Forms.Button> control to a file in isolated storage.</span></span> <span data-ttu-id="ac82f-149">`Read` Uygulama başladıktan sonra işlev'in çağrılabilir ve `Write` işlevi uygulama sona ermeden önce çağrılabilir.</span><span class="sxs-lookup"><span data-stu-id="ac82f-149">The `Read` function would be called after the application starts and the `Write` function would be called before the application ends.</span></span> <span data-ttu-id="ac82f-150">Örnek gerektiren `Read` ve `Write` işlevleri üye olarak mevcut bir <xref:System.Windows.Forms.Form> içeren bir <xref:System.Windows.Forms.Button> adlı Denetim `MainButton`.</span><span class="sxs-lookup"><span data-stu-id="ac82f-150">The example requires that the `Read` and `Write` functions exist as members of a <xref:System.Windows.Forms.Form> that contains a <xref:System.Windows.Forms.Button> control named `MainButton`.</span></span>  
  
```vb  
' Reads the button options from the isolated storage. Uses Default values   
' for the button if the options file does not exist.  
Public Sub Read()   
    Dim isoStore As System.IO.IsolatedStorage.IsolatedStorageFile = _  
        System.IO.IsolatedStorage.IsolatedStorageFile. _   
        GetUserStoreForDomain()  
  
    Dim filename As String = "options.txt"  
    Try  
        ' Checks to see if the options.txt file exists.  
        If (isoStore.GetFileNames(filename).GetLength(0) <> 0) Then  
  
            ' Opens the file because it exists.  
            Dim isos As New System.IO.IsolatedStorage.IsolatedStorageFileStream _   
                 (filename, IO.FileMode.Open,isoStore)  
            Dim reader as System.IO.StreamReader  
            Try   
                reader = new System.IO.StreamReader(isos)  
  
                ' Reads the values stored.  
                Dim converter As System.ComponentModel.TypeConverter  
                converter = System.ComponentModel.TypeDescriptor.GetConverter _   
                    (GetType(Color))  
  
                Me.MainButton.BackColor = _   
                        CType(converter.ConvertFromString _   
                         (reader.ReadLine()), Color)  
                me.MainButton.ForeColor = _  
                        CType(converter.ConvertFromString _   
                         (reader.ReadLine()), Color)  
  
                converter = System.ComponentModel.TypeDescriptor.GetConverter _   
                    (GetType(Font))  
                me.MainButton.Font = _  
                        CType(converter.ConvertFromString _   
                         (reader.ReadLine()), Font)  
  
            Catch ex As Exception  
                Debug.WriteLine("Cannot read options " + _  
                    ex.ToString())  
            Finally  
                reader.Close()  
            End Try  
        End If  
  
    Catch ex As Exception  
        Debug.WriteLine("Cannot read options " + ex.ToString())  
    End Try  
End Sub  
  
' Writes the button options to the isolated storage.  
Public Sub Write()   
    Dim isoStore As System.IO.IsolatedStorage.IsolatedStorageFile = _  
        System.IO.IsolatedStorage.IsolatedStorageFile. _   
        GetUserStoreForDomain()  
  
    Dim filename As String = "options.txt"  
    Try   
        ' Checks if the file exists, and if it does, tries to delete it.  
        If (isoStore.GetFileNames(filename).GetLength(0) <> 0) Then  
            isoStore.DeleteFile(filename)  
        End If  
    Catch ex As Exception  
        Debug.WriteLine("Cannot delete file " + ex.ToString())  
    End Try  
  
    ' Creates the options.txt file and writes the button options to it.  
    Dim writer as System.IO.StreamWriter  
    Try   
        Dim isos As New System.IO.IsolatedStorage.IsolatedStorageFileStream _   
             (filename, IO.FileMode.CreateNew, isoStore)  
  
        writer = New System.IO.StreamWriter(isos)  
        Dim converter As System.ComponentModel.TypeConverter  
  
        converter = System.ComponentModel.TypeDescriptor.GetConverter _   
           (GetType(Color))  
        writer.WriteLine(converter.ConvertToString( _  
            Me.MainButton.BackColor))  
        writer.WriteLine(converter.ConvertToString( _  
            Me.MainButton.ForeColor))  
  
        converter = System.ComponentModel TypeDescriptor.GetConverter _   
           (GetType(Font))  
        writer.WriteLine(converter.ConvertToString( _  
            Me.MainButton.Font))  
  
    Catch ex as Exception  
        Debug.WriteLine("Cannot write options " + ex.ToString())  
  
    Finally  
        writer.Close()  
    End Try  
End Sub  
```  
  
```csharp  
// Reads the button options from the isolated storage. Uses default values   
// for the button if the options file does not exist.  
public void Read()   
{  
    System.IO.IsolatedStorage.IsolatedStorageFile isoStore =   
        System.IO.IsolatedStorage.IsolatedStorageFile.  
        GetUserStoreForDomain();  
  
    string filename = "options.txt";  
    try  
    {  
        // Checks to see if the options.txt file exists.  
        if (isoStore.GetFileNames(filename).GetLength(0) != 0)   
        {  
            // Opens the file because it exists.  
            System.IO.IsolatedStorage.IsolatedStorageFileStream isos =   
                new System.IO.IsolatedStorage.IsolatedStorageFileStream  
                    (filename, System.IO.FileMode.Open,isoStore);  
            System.IO.StreamReader reader = null;  
            try   
            {  
                reader = new System.IO.StreamReader(isos);  
  
                // Reads the values stored.  
                TypeConverter converter ;  
                converter = TypeDescriptor.GetConverter(typeof(Color));  
  
                this.MainButton.BackColor =   
                 (Color)(converter.ConvertFromString(reader.ReadLine()));  
                this.MainButton.ForeColor =   
                 (Color)(converter.ConvertFromString(reader.ReadLine()));  
  
                converter = TypeDescriptor.GetConverter(typeof(Font));  
                this.MainButton.Font =   
                  (Font)(converter.ConvertFromString(reader.ReadLine()));  
            }  
            catch (Exception ex)  
            {   
                System.Diagnostics.Debug.WriteLine  
                     ("Cannot read options " + ex.ToString());  
            }  
            finally  
            {  
                reader.Close();  
            }  
        }  
    }   
    catch (Exception ex)   
    {  
        System.Diagnostics.Debug.WriteLine  
            ("Cannot read options " + ex.ToString());  
    }  
}  
  
// Writes the button options to the isolated storage.  
public void Write()   
{  
    System.IO.IsolatedStorage.IsolatedStorageFile isoStore =   
        System.IO.IsolatedStorage.IsolatedStorageFile.  
        GetUserStoreForDomain();  
  
    string filename = "options.txt";  
    try   
    {  
        // Checks if the file exists and, if it does, tries to delete it.  
        if (isoStore.GetFileNames(filename).GetLength(0) != 0)   
        {  
            isoStore.DeleteFile(filename);  
        }  
    }  
    catch (Exception ex)   
    {  
        System.Diagnostics.Debug.WriteLine  
            ("Cannot delete file " + ex.ToString());  
    }  
  
    // Creates the options file and writes the button options to it.  
    System.IO.StreamWriter writer = null;  
    try   
    {  
        System.IO.IsolatedStorage.IsolatedStorageFileStream isos = new   
            System.IO.IsolatedStorage.IsolatedStorageFileStream(filename,   
            System.IO.FileMode.CreateNew,isoStore);  
  
        writer = new System.IO.StreamWriter(isos);  
        TypeConverter converter ;  
  
        converter = TypeDescriptor.GetConverter(typeof(Color));  
        writer.WriteLine(converter.ConvertToString(  
            this.MainButton.BackColor));  
        writer.WriteLine(converter.ConvertToString(  
            this.MainButton.ForeColor));  
  
        converter = TypeDescriptor.GetConverter(typeof(Font));  
        writer.WriteLine(converter.ConvertToString(  
            this.MainButton.Font));  
  
    }  
    catch (Exception ex)  
    {   
        System.Diagnostics.Debug.WriteLine  
           ("Cannot write options " + ex.ToString());  
    }  
    finally  
    {  
        writer.Close();  
    }  
}  
```  
  
## <a name="database-access"></a><span data-ttu-id="ac82f-151">Veritabanı erişimi</span><span class="sxs-lookup"><span data-stu-id="ac82f-151">Database Access</span></span>  
 <span data-ttu-id="ac82f-152">Bir veritabanına erişmek için gerekli izinleri veritabanı sağlayıcısı bağlı olarak farklılık; Ancak, uygun izinlerle çalışmakta olan uygulamalar bir veritabanı bir veri bağlantısı üzerinden erişebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="ac82f-152">The permissions required to access a database vary based on the database provider; however, only applications that are running with the appropriate permissions can access a database through a data connection.</span></span> <span data-ttu-id="ac82f-153">Bir veritabanına erişmek için gereken izinler hakkında daha fazla bilgi için bkz: [kod erişim güvenliği ve ADO.NET](../../../docs/framework/data/adonet/code-access-security.md).</span><span class="sxs-lookup"><span data-stu-id="ac82f-153">For more information about the permissions that are required to access a database, see [Code Access Security and ADO.NET](../../../docs/framework/data/adonet/code-access-security.md).</span></span>  
  
 <span data-ttu-id="ac82f-154">Kısmi güvende çalıştırmak için uygulamanızın istediğinden doğrudan bir veritabanı erişemiyorsanız, verilerinize erişmek bir alternatif anlamına gelir gibi bir Web hizmetini kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="ac82f-154">If you cannot directly access a database because you want your application to run in partial trust, you can use a Web service as an alternative means to access your data.</span></span> <span data-ttu-id="ac82f-155">Bir Web hizmeti, bir ağ üzerinden programlı olarak erişilebilir yazılım parçasıdır.</span><span class="sxs-lookup"><span data-stu-id="ac82f-155">A Web service is a piece of software that can be programmatically accessed over a network.</span></span> <span data-ttu-id="ac82f-156">Web Hizmetleri ile uygulamaları kodu Grup dilimlerinde veri paylaşabilir.</span><span class="sxs-lookup"><span data-stu-id="ac82f-156">With Web services, applications can share data across code group zones.</span></span> <span data-ttu-id="ac82f-157">Varsayılan olarak, yerel intranet ve Internet bölgeleri uygulamalarda sitelerinin bunları aynı sunucu üzerinde barındırılan bir Web hizmetini çağırmak etkinleştirir kaynak erişim hakkı verilir.</span><span class="sxs-lookup"><span data-stu-id="ac82f-157">By default, applications in the local intranet and Internet zones are granted the right to access their sites of origin, which enables them to call a Web service hosted on the same server.</span></span> <span data-ttu-id="ac82f-158">Daha fazla bilgi için bkz: [ASP.NET AJAX Web hizmetlerinde](http://msdn.microsoft.com/en-us/8290e543-7eff-47a4-aace-681f3c07229b) veya [Windows Communication Foundation](http://msdn.microsoft.com/library/ms735119.aspx).</span><span class="sxs-lookup"><span data-stu-id="ac82f-158">For more information see [Web Services in ASP.NET AJAX](http://msdn.microsoft.com/en-us/8290e543-7eff-47a4-aace-681f3c07229b) or [Windows Communication Foundation](http://msdn.microsoft.com/library/ms735119.aspx).</span></span>  
  
## <a name="registry-access"></a><span data-ttu-id="ac82f-159">Kayıt defteri erişimi</span><span class="sxs-lookup"><span data-stu-id="ac82f-159">Registry Access</span></span>  
 <span data-ttu-id="ac82f-160"><xref:System.Security.Permissions.RegistryPermission> Sınıfı işletim sisteminin kayıt defterine erişim denetler.</span><span class="sxs-lookup"><span data-stu-id="ac82f-160">The <xref:System.Security.Permissions.RegistryPermission> class controls access to the operating system registry.</span></span> <span data-ttu-id="ac82f-161">Varsayılan olarak, yerel olarak çalışan yalnızca uygulamaları kayıt erişebilir.</span><span class="sxs-lookup"><span data-stu-id="ac82f-161">By default, only applications that are running locally can access the registry.</span></span>  <span data-ttu-id="ac82f-162"><xref:System.Security.Permissions.RegistryPermission>yalnızca bir uygulama kayıt defteri erişimi deneyin hakkı verir; işletim sistemi hala kayıt defterindeki güvenlik zorladığından, erişim başarılı olur, garanti etmez.</span><span class="sxs-lookup"><span data-stu-id="ac82f-162"><xref:System.Security.Permissions.RegistryPermission> only grants an application the right to try registry access; it does not guarantee access will succeed, because the operating system still enforces security on the registry.</span></span>  
  
 <span data-ttu-id="ac82f-163">Kısmi güven altında kayıt defterine erişemediği için diğer yöntemleri, veri depolamanın bulmak gerekebilir.</span><span class="sxs-lookup"><span data-stu-id="ac82f-163">Because you cannot access the registry under partial trust, you may need to find other methods of storing your data.</span></span> <span data-ttu-id="ac82f-164">Uygulama ayarlarını depolamak, yalıtılmış depolama kayıt defteri yerine kullanın.</span><span class="sxs-lookup"><span data-stu-id="ac82f-164">When you store application settings, use isolated storage instead of the registry.</span></span> <span data-ttu-id="ac82f-165">Yalıtılmış Depolama, diğer uygulamaya özgü dosyalarını depolamak için de kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="ac82f-165">Isolated storage can also be used to store other application-specific files.</span></span> <span data-ttu-id="ac82f-166">Varsayılan olarak, uygulamanın kendi kaynak site erişim hakkı verilir çünkü sunucu veya siteyle kaynak, genel uygulama bilgilerini de depolayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="ac82f-166">You can also store global application information about the server or site of origin, because by default an application is granted the right to access the site of its origin.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac82f-167">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="ac82f-167">See Also</span></span>  
 [<span data-ttu-id="ac82f-168">Windows Forms'ta daha güvenli yazdırma</span><span class="sxs-lookup"><span data-stu-id="ac82f-168">More Secure Printing in Windows Forms</span></span>](../../../docs/framework/winforms/more-secure-printing-in-windows-forms.md)  
 [<span data-ttu-id="ac82f-169">Windows Forms'ta ek güvenlik konuları</span><span class="sxs-lookup"><span data-stu-id="ac82f-169">Additional Security Considerations in Windows Forms</span></span>](../../../docs/framework/winforms/additional-security-considerations-in-windows-forms.md)  
 [<span data-ttu-id="ac82f-170">Windows Forms'a genel bakış güvenliği</span><span class="sxs-lookup"><span data-stu-id="ac82f-170">Security in Windows Forms Overview</span></span>](../../../docs/framework/winforms/security-in-windows-forms-overview.md)  
 [<span data-ttu-id="ac82f-171">Windows Forms güvenliği</span><span class="sxs-lookup"><span data-stu-id="ac82f-171">Windows Forms Security</span></span>](../../../docs/framework/winforms/windows-forms-security.md)  
 [<span data-ttu-id="ac82f-172">Mage.exe (bildirim üretme ve düzenleme aracı)</span><span class="sxs-lookup"><span data-stu-id="ac82f-172">Mage.exe (Manifest Generation and Editing Tool)</span></span>](../../../docs/framework/tools/mage-exe-manifest-generation-and-editing-tool.md)  
 [<span data-ttu-id="ac82f-173">MageUI.exe (bildirim üretme ve düzenleme aracı, grafik istemci)</span><span class="sxs-lookup"><span data-stu-id="ac82f-173">MageUI.exe (Manifest Generation and Editing Tool, Graphical Client)</span></span>](../../../docs/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client.md)