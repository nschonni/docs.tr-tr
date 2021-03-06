---
title: "Nasıl yapılır: İçeriğin FlowDirection'ını Program Aracılığıyla Değiştirme"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- FlowDirection property [WPF], changing programmatically
- documents [WPF], changing FlowDirection property programmatically
ms.assetid: 02f5a8ba-f8c0-4e5a-84b9-4c5bf12922a2
ms.openlocfilehash: 97a64ad54384077a15a643dc528d043b2ef6627a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33543412"
---
# <a name="how-to-change-the-flowdirection-of-content-programmatically"></a>Nasıl yapılır: İçeriğin FlowDirection'ını Program Aracılığıyla Değiştirme
Bu örnek programlı olarak nasıl değiştirildiğini gösterir <xref:System.Windows.FrameworkElement.FlowDirection%2A> özelliği bir <xref:System.Windows.Controls.FlowDocumentReader>.  
  
## <a name="example"></a>Örnek  
 İki <xref:System.Windows.Controls.Button> öğeleri oluşturulur ve her bir olası değerlerini temsil eden <xref:System.Windows.FlowDirection>. Düğme tıklatıldığında ilişkili özellik değeri içeriğini uygulanan bir <xref:System.Windows.Controls.FlowDocumentReader> adlı `tf1`.  Özellik değeri de yazılan bir <xref:System.Windows.Controls.TextBlock> adlı `txt1`.  
  
 [!code-xaml[FlowDirectionSnippets#_FlowDirectionXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDirectionSnippets/CSharp/Window1.xaml#_flowdirectionxaml)]  
  
## <a name="example"></a>Örnek  
 Yukarıda tanımlanan düğme tıklama ile ilişkili olayları bir C# arka plan kod dosyasına işlenir.  
  
 [!code-csharp[FlowDirectionSnippets#_FlowDirection](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDirectionSnippets/CSharp/Window1.xaml.cs#_flowdirection)]
 [!code-vb[FlowDirectionSnippets#_FlowDirection](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDirectionSnippets/VisualBasic/Window1.xaml.vb#_flowdirection)]
