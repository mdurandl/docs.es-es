---
title: Errores en sesiones de mensajería de confianza por segundo
ms.date: 03/30/2017
ms.assetid: 8f8ca2eb-1be4-4b6a-aa78-fcd3ee145fe8
ms.openlocfilehash: c77d6a5f12dcce15dba94e2f63025a219ebcc6fd
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2018
ms.locfileid: "45964610"
---
# <a name="reliable-messaging-sessions-faulted-per-second"></a>Errores en sesiones de mensajería de confianza por segundo
Nombre de contador: errores en las sesiones de mensajería de confianza por segundo.  
  
## <a name="description"></a>Descripción  
 Número de sesiones de mensajería confiables que tienen un error en este servicio en un segundo.  
  
 Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), cuyo valor se calcula mediante la siguiente fórmula.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
