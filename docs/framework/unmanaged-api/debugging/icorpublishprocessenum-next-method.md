---
title: ICorPublishProcessEnum::Next (Método)
ms.date: 03/30/2017
api_name:
- ICorPublishProcessEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcessEnum::Next
helpviewer_keywords:
- ICorPublishProcessEnum::Next method [.NET Framework debugging]
- Next method, ICorPublishProcessEnum interface [.NET Framework debugging]
ms.assetid: 6c399f37-1e38-4ca1-b70d-8ae41f7228b7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e427c3919e8b714146fbe630a7e151dff10703de
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54582419"
---
# <a name="icorpublishprocessenumnext-method"></a>ICorPublishProcessEnum::Next (Método)
Obtiene el número especificado de procesos de la colección, empezando en la posición actual del cursor.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorPublishProcess **objects,  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `celt`  
 [in] El número de procesos que va a recuperar.  
  
 `objects`  
 [out] Recupera un puntero a la matriz de [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) objetos, cada uno de los cuales representa un proceso.  
  
 `pceltFetched`  
 [out] Puntero al número de procesos devueltos realmente. Este valor puede ser null si `celt` es uno.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorPub.idl, CorPub.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [ICorPublishProcessEnum (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md)
