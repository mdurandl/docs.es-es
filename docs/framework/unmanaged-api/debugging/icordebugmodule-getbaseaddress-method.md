---
title: ICorDebugModule::GetBaseAddress (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetBaseAddress
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetBaseAddress
helpviewer_keywords:
- GetBaseAddress method [.NET Framework debugging]
- ICorDebugModule::GetBaseAddress method [.NET Framework debugging]
ms.assetid: 26a82815-1982-4eb7-92d1-5c3d318d5be4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7ad6c8bd59f62bc7b0a96e1ef5e545fe15610c91
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54516985"
---
# <a name="icordebugmodulegetbaseaddress-method"></a>ICorDebugModule::GetBaseAddress (Método)
Obtiene la dirección base del módulo.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetBaseAddress(  
    [out] CORDB_ADDRESS *pAddress  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `pAddress`  
 [out] Un `CORDB_ADDRESS` que especifica la dirección base del módulo.  
  
## <a name="remarks"></a>Comentarios  
 Si el módulo es nativo de imagen (es decir, si el módulo se ha producido por el generador de imágenes nativas, NGen.exe), su dirección base será cero.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también


