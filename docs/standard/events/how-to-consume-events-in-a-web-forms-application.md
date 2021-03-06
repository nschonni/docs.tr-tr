---
title: 'Nasıl yapılır: Bir Windows Formları Uygulamasında Olayları Kullanma'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- events [.NET Framework], Web Forms
- Web Forms controls, and events
- event handlers [.NET Framework], Web Forms
- events [.NET Framework], consuming
- Web Forms, event handling
ms.assetid: 73bf8638-c4ec-4069-b0bb-a1dc79b92e32
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c03ab0e1d493d9669f1e3821393d41d1c1b89867
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/09/2018
ms.locfileid: "44227551"
---
# <a name="how-to-consume-events-in-a-web-forms-application"></a>Nasıl yapılır: Bir Windows Formları Uygulamasında Olayları Kullanma
ASP.NET Web Forms uygulamalarında yaygın bir senaryo, bir Web sayfası denetimleri ile doldurun ve ardından, kullanıcı denetimi dayalı belirli bir eylemi gerçekleştirmek sağlamaktır. Örneğin, bir <xref:System.Web.UI.WebControls.Button?displayProperty=nameWithType> denetimi, kullanıcının Web sayfasında tıkladığında bir olay başlatır. Olayını işleyerek, uygulamanız için bu düğmeye tıklayın uygun uygulama mantığını gerçekleştirebilirsiniz.  
  
### <a name="to-handle-a-button-click-event-on-a-webpage"></a>Bir Web sayfasında düğme tıklatma olayını işlemek için  
  
1.  Sahip bir ASP.NET Web Forms sayfası (Web sayfası) oluşturun bir <xref:System.Web.UI.WebControls.Button> denetimini `OnClick` değerine sonraki adımda tanımlayacak yöntemin adı.  
  
    ```xml  
    <asp:Button ID="Button1" runat="server" Text="Click Me" OnClick="Button1_Click" />  
    ```  
  
2.  Eşleşen bir olay işleyicisi tanımlama <xref:System.Web.UI.WebControls.Button.Click> olay temsilci imzası ve bu sahip için tanımlanan adını `OnClick` değeri.  
  
    ```csharp  
    protected void Button1_Click(object sender, EventArgs e)  
    {  
        // perform action  
    }  
    ```  
  
    ```vb  
    Protected Sub Button1_Click(sender As Object, e As EventArgs) Handles Button1.Click  
        ' perform action  
    End Sub  
    ```  
  
     <xref:System.Web.UI.WebControls.Button.Click> Olay kullanır <xref:System.EventHandler> temsilci türü için sınıf ve <xref:System.EventArgs> olay veri sınıfı. ASP.NET sayfası framework örneği oluşturan kodu otomatik olarak oluşturduğu <xref:System.EventHandler> ve bu temsilci örneğine ekler <xref:System.Web.UI.WebControls.Button.Click> olayı <xref:System.Web.UI.WebControls.Button> örneği.  
  
3.  Olay işleyicisi yöntemi, 2. adımda tanımladığınız olay gerçekleştiğinde, gerekli olan herhangi bir eylem gerçekleştirmek için kod ekleyin.  
  
## <a name="see-also"></a>Ayrıca bkz.

- [Olaylar](../../../docs/standard/events/index.md)
