---
title: srv_willconvert (интерфейс API расширенных хранимых процедур) | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_willconvert
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_willconvert
ms.assetid: 6f4db5fd-215a-461c-95e4-17697852733e
author: rothja
ms.author: jroth
ms.openlocfilehash: 0b9adfbd2a73b30cbfc0229b7942f79d3ddc1a82
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751011"
---
# <a name="srv_willconvert-extended-stored-procedure-api"></a>srv_willconvert (API-интерфейс расширенных хранимых процедур)
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] Используйте вместо этого интеграцию со средой CLR.  
  
 Определяет, доступно ли конкретное преобразование типов данных в библиотеке ODS.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
BOOL srv_willconvert (  
int  
srctype  
,  
int  
desttype   
);  
  
```  
  
## <a name="arguments"></a>Аргументы  
 *srctype*  
 Указывает тип преобразуемых данных. Этот параметр может иметь любой из типов данных API-интерфейса расширенных хранимых процедур.  
  
 *desttype*  
 Указывает тип данных, в который преобразуются исходные данные. Этот параметр может иметь любой из типов данных API-интерфейса расширенных хранимых процедур.  
  
## <a name="returns"></a>Возвращаемое значение  
 Значение TRUE, если преобразование типов данных поддерживается, значение FALSE, если преобразование типов данных не поддерживается.  
  
## <a name="remarks"></a>Remarks  
 Описание каждого типа данных см. в разделе [Типы данных (интерфейс API расширенных хранимых процедур)](data-types-extended-stored-procedure-api.md).  
  
> [!IMPORTANT]  
>  Необходимо тщательно просмотреть исходный код расширенных хранимых процедур и проверить скомпилированные библиотеки DLL перед их установкой на рабочий сервер. Сведения о проверке безопасности см. на следующем [веб-сайте Майкрософт](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).  
  
## <a name="see-also"></a>См. также:  
 [srv_convert (интерфейс API расширенных хранимых процедур)](srv-convert-extended-stored-procedure-api.md)  
  
  
