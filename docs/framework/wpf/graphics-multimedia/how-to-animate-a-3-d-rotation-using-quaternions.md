---
title: Filtrar Animar un giro 3D mediante cuaterniones
ms.date: 03/30/2017
helpviewer_keywords:
- quaternions [WPF]
- animation [WPF], 3-D translations [WPF], with quaternions
- 3-D translations [WPF], animating [WPF], with quaternions
ms.assetid: adca9cb1-066b-4de8-abbb-6b4007579ee7
ms.openlocfilehash: 079358ec12da803c8aa497bce1c272fa51f1c3b5
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57368576"
---
# <a name="how-to-animate-a-3-d-rotation-using-quaternions"></a>Filtrar Animar un giro 3D mediante cuaterniones
En este ejemplo se muestra cómo animar un giro de un objeto 3D mediante cuaterniones.  
  
 El código siguiente muestra un <xref:System.Windows.Media.Media3D.QuaternionRotation3D> utilizar como el valor de la <xref:System.Windows.Media.Media3D.RotateTransform3D.Rotation%2A> propiedad de un <xref:System.Windows.Media.Media3D.RotateTransform3D>.  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexampleinline1)]  
  
 Esto <xref:System.Windows.Media.Media3D.QuaternionRotation3D> está animada con un <xref:System.Windows.Media.Animation.QuaternionAnimation> dentro de un <xref:System.Windows.Media.Animation.Storyboard> con el código siguiente.  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexampleinline2)]  
  
## <a name="example"></a>Ejemplo  
 El código siguiente muestra el ejemplo completo.  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexamplewholepage)]  
  
## <a name="see-also"></a>Vea también
- [Información general sobre animaciones](animation-overview.md)
- [Crear una escena 3D](how-to-create-a-3-d-scene.md)
- [Información general sobre gráficos 3D](3-d-graphics-overview.md)
- [Información general sobre transformaciones](transforms-overview.md)
- [Animar un giro 3D mediante Storyboards](how-to-animate-a-3-d-rotation-using-storyboards.md)
- [Animar un giro 3D mediante Rotation3DAnimation](how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
