---
title: 'Nasıl yapılır: WebRequest ile eşleşen protokole özgü WebResponse alma'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d8c90785-f16b-42a5-8439-ed2f731b2ba8
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 2a72e57156903c9d436a49aaf6da596868af4003
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2018
ms.locfileid: "48581855"
---
# <a name="how-to-retrieve-a-protocol-specific-webresponse-that-matches-a-webrequest"></a>Nasıl yapılır: WebRequest ile eşleşen protokole özgü WebResponse alma
Bu örnekte, WebRequest ile eşleşen protokole özgü WebResponse alma gösterilmektedir.  
  
## <a name="example"></a>Örnek  
  
```csharp  
WebRequest req = WebRequest.Create("http://www.contoso.com/");  
WebResponse resp = req.GetResponse();  
```  
  
```vb  
Dim req As WebRequest = WebRequest.Create("http://www.contoso.com")  
Dim resp As WebResponse = req.GetResponse()  
```  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
 Bu örnek gerektirir:  
  
-   Başvurular **System.Net** ad alanı.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Veri İsteme](../../../docs/framework/network-programming/requesting-data.md)
