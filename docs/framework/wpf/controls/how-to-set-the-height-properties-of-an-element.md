---
title: Procedimiento Establecer las propiedades de alto de un elemento
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- height properties [WPF]
- Panel control [WPF], height properties of elements
ms.assetid: 5ab9e781-dbb8-469a-a3c8-cf38ce312647
ms.openlocfilehash: 608f74afd95ce03b3ecf71819c2181a9728b25af
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57356301"
---
# <a name="how-to-set-the-height-properties-of-an-element"></a>Filtrar Establecer las propiedades de alto de un elemento
## <a name="example"></a>Ejemplo  
 Este ejemplo muestran las diferencias de comportamiento entre las cuatro propiedades de altura en representación [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  
  
 La <xref:System.Windows.FrameworkElement> clase expone cuatro propiedades que describen las características de alto de un elemento. Estas cuatro propiedades pueden entrar en conflicto y, cuando lo hacen, el valor que tiene prioridad se determina como sigue: el <xref:System.Windows.FrameworkElement.MinHeight%2A> valor tiene prioridad sobre la <xref:System.Windows.FrameworkElement.MaxHeight%2A> valor, que a su vez tiene prioridad sobre la <xref:System.Windows.FrameworkElement.Height%2A> valor. Una propiedad de la cuarta, <xref:System.Windows.FrameworkElement.ActualHeight%2A>, es de solo lectura y notifica el alto real determinado por las interacciones con el proceso de diseño.  
  
 La siguiente [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] ejemplos dibujar un <xref:System.Windows.Shapes.Rectangle> elemento (`rect1`) como un elemento secundario de <xref:System.Windows.Controls.Canvas>. Puede cambiar las propiedades de alto de un <xref:System.Windows.Shapes.Rectangle> mediante el uso de una serie de <xref:System.Windows.Controls.ListBox> elementos que representan los valores de propiedad <xref:System.Windows.FrameworkElement.MinHeight%2A>, <xref:System.Windows.FrameworkElement.MaxHeight%2A>, y <xref:System.Windows.FrameworkElement.Height%2A>. De esta manera, se muestra gráficamente la prioridad de cada propiedad.  
  
 [!code-xaml[HeightMinHeightMaxHeight#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml#1)]  
[!code-xaml[HeightMinHeightMaxHeight#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml#2)]  
  
 Los siguientes ejemplos de código subyacente controlan los eventos que el <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> provoca el evento. Cada controlador toma la entrada de la <xref:System.Windows.Controls.ListBox>, analiza el valor como un <xref:System.Double>y se aplica el valor a la propiedad relacionada con el alto especificada. Los valores alto también se convierten en una cadena y escritos en varios <xref:System.Windows.Controls.TextBlock> elementos (definición de esos elementos no se muestra en el XAML seleccionado).  
  
 [!code-csharp[HeightMinHeightMaxHeight#3](~/samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml.cs#3)]
 [!code-vb[HeightMinHeightMaxHeight#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HeightMinHeightMaxHeight/VisualBasic/Window1.xaml.vb#3)]  
  
 Para obtener un ejemplo completo, vea [alto propiedades ejemplo](https://go.microsoft.com/fwlink/?LinkID=159993).  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.FrameworkElement>
- <xref:System.Windows.Controls.ListBox>
- <xref:System.Windows.FrameworkElement.ActualHeight%2A>
- <xref:System.Windows.FrameworkElement.MaxHeight%2A>
- <xref:System.Windows.FrameworkElement.MinHeight%2A>
- <xref:System.Windows.FrameworkElement.Height%2A>
- [Establecer las propiedades de ancho de un elemento](how-to-set-the-width-properties-of-an-element.md)
- [Información general sobre elementos Panel](panels-overview.md)
- [Ejemplo de propiedades de alto](https://go.microsoft.com/fwlink/?LinkID=159993)
