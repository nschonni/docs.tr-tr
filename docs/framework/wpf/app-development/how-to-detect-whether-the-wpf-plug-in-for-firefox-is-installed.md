---
title: "Nasıl yapılır: Firefox WPF Eklentisinin Yüklü Olup Olmadığını Algılama"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- plug-in for Firefox [WPF]
- detecting Firefox installation [WPF]
- checking for the Firefox plug-in [WPF]
- Firefox [WPF], detecting installation
- detecting whether the WPF plug-in for Firefox is installed [WPF]
ms.assetid: 5f839373-e3fb-44f1-88ad-4a0761f02189
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3012afc118420a83c869785d26c28f1eee969cb3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-detect-whether-the-wpf-plug-in-for-firefox-is-installed"></a><span data-ttu-id="20e4c-102">Nasıl yapılır: Firefox WPF Eklentisinin Yüklü Olup Olmadığını Algılama</span><span class="sxs-lookup"><span data-stu-id="20e4c-102">How to: Detect Whether the WPF Plug-In for Firefox Is Installed</span></span>
<span data-ttu-id="20e4c-103">[!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] Firefox etkinleştirir eklenti [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] ve kaybetmiş Mozilla Firefox tarayıcıda çalıştırmak için XAML dosyaları.</span><span class="sxs-lookup"><span data-stu-id="20e4c-103">The [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] plug-in for Firefox enables [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] and loose XAML files to run in the Mozilla Firefox browser.</span></span> <span data-ttu-id="20e4c-104">Bu konu, HTML ve yöneticilerin Firefox WPF eklentisinin yüklü olup olmadığını belirlemek için kullanabileceğiniz JavaScript yazılmış bir betik sağlar.</span><span class="sxs-lookup"><span data-stu-id="20e4c-104">This topic provides a script written in HTML and JavaScript that administrators can use to determine whether the WPF plug-in for Firefox is installed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="20e4c-105">Yükleme, dağıtma ve algılama hakkında daha fazla bilgi için [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], bkz: [geliştiriciler için .NET Framework'ü yüklemek](../../../../docs/framework/install/guide-for-developers.md).</span><span class="sxs-lookup"><span data-stu-id="20e4c-105">For more information about installing, deploying, and detecting the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], see [Install the .NET Framework for developers](../../../../docs/framework/install/guide-for-developers.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="20e4c-106">Örnek</span><span class="sxs-lookup"><span data-stu-id="20e4c-106">Example</span></span>  
 <span data-ttu-id="20e4c-107">Zaman [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)] olan yüklü istemci bilgisayar Firefox WPF eklentisi ile yapılandırılır.</span><span class="sxs-lookup"><span data-stu-id="20e4c-107">When the [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)] is installed, the client computer is configured with a WPF plug-in for Firefox.</span></span> <span data-ttu-id="20e4c-108">Aşağıdaki örnek betik, Firefox WPF eklentisini denetler ve uygun durum iletisini görüntüler.</span><span class="sxs-lookup"><span data-stu-id="20e4c-108">The following example script checks for the WPF plug-in for Firefox and then displays an appropriate status message.</span></span>  
  
```  
<HTML>  
  
  <HEAD>  
    <TITLE>Test for the WPF plug-in for Firefox</TITLE>  
    <META HTTP-EQUIV="Content-Type" CONTENT="text/html; charset=utf-8" />  
    <SCRIPT type="text/javascript">  
    <!--  
    function OnLoad()  
    {  
  
       // Check for the WPF plug-in for Firefox and report  
       var msg = "The WPF plug-in for Firefox is ";  
       var wpfPlugin = navigator.plugins["Windows Presentation Foundation"];  
       if( wpfPlugin != null ) {  
          document.writeln(msg + " installed.");  
       }  
       else {  
          document.writeln(msg + " not installed. Please install or reinstall the .NET Framework 3.5.");  
       }  
    }  
    -->  
    </SCRIPT>  
  </HEAD>  
  
  <BODY onload="OnLoad()" />  
  
</HTML>  
```  
  
 <span data-ttu-id="20e4c-109">Firefox WPF eklentisi denetle başarılı olursa, aşağıdaki durum iletisi görüntülenir:</span><span class="sxs-lookup"><span data-stu-id="20e4c-109">If the check for the WPF plug-in for Firefox is successful, the following status message is displayed:</span></span>  
  
 `The WPF plug-in for Firefox is installed.`  
  
 <span data-ttu-id="20e4c-110">Aksi takdirde, aşağıdaki durum iletisi görüntülenir:</span><span class="sxs-lookup"><span data-stu-id="20e4c-110">Otherwise, the following status message is displayed:</span></span>  
  
 `The WPF plug-in for Firefox is not installed. Please install or reinstall the .NET Framework 3.5.`  
  
## <a name="see-also"></a><span data-ttu-id="20e4c-111">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="20e4c-111">See Also</span></span>  
 [<span data-ttu-id="20e4c-112">.NET Framework 3.0 yüklü olup olmadığını Algıla</span><span class="sxs-lookup"><span data-stu-id="20e4c-112">Detect Whether the .NET Framework 3.0 Is Installed</span></span>](../../../../docs/framework/wpf/app-development/how-to-detect-whether-the-net-framework-3-0-is-installed.md)  
 [<span data-ttu-id="20e4c-113">.NET Framework 3.5 yüklü olup olmadığını Algıla</span><span class="sxs-lookup"><span data-stu-id="20e4c-113">Detect Whether the .NET Framework 3.5 Is Installed</span></span>](../../../../docs/framework/wpf/app-development/how-to-detect-whether-the-net-framework-3-5-is-installed.md)  
 [<span data-ttu-id="20e4c-114">WPF XAML tarayıcısı uygulamaları genel bakış</span><span class="sxs-lookup"><span data-stu-id="20e4c-114">WPF XAML Browser Applications Overview</span></span>](../../../../docs/framework/wpf/app-development/wpf-xaml-browser-applications-overview.md)