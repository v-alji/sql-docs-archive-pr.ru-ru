---
title: srv_paraminfo (интерфейс API расширенных хранимых процедур) | Документы Майкрософт
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_paraminfo
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_paraminfo
ms.assetid: ee2afd4e-0d91-462b-9403-98d481546330
author: rothja
ms.author: jroth
ms.openlocfilehash: cc3d51acc2ca560246c46267840db72934223999
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751036"
---
# <a name="srv_paraminfo-extended-stored-procedure-api"></a>srv_paraminfo (API-интерфейс расширенных хранимых процедур)
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] Используйте вместо этого интеграцию со средой CLR.  
  
 Возвращает сведения о параметре. Эта функция заменяет следующие: [srv_paramtype](srv-paramtype-extended-stored-procedure-api.md), [srv_paramlen](srv-paramlen-extended-stored-procedure-api.md), [srv_parammaxlen](srv-parammaxlen-extended-stored-procedure-api.md) и [srv_paramdata](srv-paramdata-extended-stored-procedure-api.md). **srv_paraminfo** поддерживает типы данных, указанные в разделе [Типы данных](data-types-extended-stored-procedure-api.md), и данные нулевой длины.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
int srv_paraminfo (  
SRV_PROC *  
srvproc  
,  
int  
n  
,  
BYTE *  
pbType  
,  
ULONG *  
pcbMaxLen  
,  
ULONG *  
pcbActualLen  
,  
BYTE *  
pbData  
,  
BOOL *  
pfNull  
);  
  
```  
  
## <a name="arguments"></a>Аргументы  
 *srvproc*  
 Дескриптор для клиентского соединения.  
  
 *n*  
 Порядковый номер устанавливаемого столбца. Первый параметр имеет значение 1.  
  
 *pbType*  
 Тип данных параметра.  
  
 *pcbMaxLen*  
 Указатель на максимальную длину параметра.  
  
 *pcbActualLen*  
 Указатель на фактическую длину параметра. Значение 0 (\**pcbActualLen* == 0) указывает на данные нулевой длины, если значение **pfNull* равно FALSE.  
  
 *pbData*  
 Указатель на буфер данных параметра. Если значение *pbData* не равно NULL, интерфейс API расширенных хранимых процедур записывает \**pcbActualLen* байт данных в \**pbData*. Если *pbData* имеет значение NULL, данные в \**pbData* не записываются, но функция возвращает \**pbType*, \**pcbMaxLen*, \**pcbActualLen* и **pfNull*. Управление памятью для этого буфера должно осуществляться приложением.  
  
 *pfNull*  
 Указатель на флаг null **pfNull* устанавливается в значение TRUE, если параметр имеет значение NULL.  
  
## <a name="returns"></a>Возвращаемое значение  
 При успешном получении сведений о параметре возвращается значение SUCCEED; в иных случаях – значение FAIL. Значение FAIL возвращается, если удаленной хранимой процедуры сейчас не существует или у нее нет параметра с номером *n*.  
  
## <a name="remarks"></a>Remarks  
 **Примечание по безопасности.** Необходимо тщательно просмотреть исходный код расширенных хранимых процедур и проверить скомпилированные DLL-библиотеки перед их установкой на рабочий сервер. Сведения о проверке безопасности см. на следующем [веб-сайте Майкрософт](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).  
  
## <a name="see-also"></a>См. также:  
 [Справочник по программированию расширенных хранимых процедур](database-engine-extended-stored-procedures-reference.md)  
  
  
