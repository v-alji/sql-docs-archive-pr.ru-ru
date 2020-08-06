---
title: IBCPSession::BCPWriteFmt (OLE DB) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- IBCPSession::BCPWriteFmt (OLE DB)
topic_type:
- apiref
helpviewer_keywords:
- BCPWriteFmt method
ms.assetid: add50425-2ed6-411a-a391-4ce63c364892
author: rothja
ms.author: jroth
ms.openlocfilehash: ee4dcb5809c0f0fbb6d3f7aba6f4af5f6991e0e8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667718"
---
# <a name="ibcpsessionbcpwritefmt-ole-db"></a>IBCPSession::BCPWriteFmt (OLE DB)
  Записывает в файл форматирования сведения о формате каждого из столбцов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
HRESULT BCPWriteFmt(   
const wchar_t *pwszFormatFile);  
```  
  
## <a name="remarks"></a>Remarks  
 Файл форматирования определяет формат данных, содержащихся в файле данных, создаваемом при массовом копировании. Вызовы методов [IBCPSession::BCPColumns](ibcpsession-bcpcolumns-ole-db.md) и [IBCPSession::BCPColFmt](ibcpsession-bcpcolfmt-ole-db.md) определяют формат файла данных. Метод **BCPWriteFmt** сохраняет это определение в файле, на который ссылается аргумент pwszFormatFile.  
  
 Метод **BCPWriteFmt** может сохранять файлы форматирования в формате xml или текстовом формате. Это должно определяться с помощью параметра управления BCP_OPTION_XML методом [IBCPSession::BCPControl](ibcpsession-bcpcontrol-ole-db.md).  
  
 Для загрузки сохраненного файла форматирования используется метод [IBCPSession::BCPReadFmt](ibcpsession-bcpreadfmt-ole-db.md).  
  
## <a name="arguments"></a>Аргументы  
 *pwszFormatFile*[in]  
 Путь и имя файла, содержащего значения формата для файла данных.  
  
## <a name="return-code-values"></a>Значения кода возврата  
 S_OK  
 Метод выполнен успешно.  
  
 E_FAIL  
 Произошла ошибка конкретного поставщика; для получения дополнительных сведений используйте интерфейс [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md) .  
  
 E_OUTOFMEMORY  
 Недостаточно памяти.  
  
 E_UNEXPECTED  
 Непредвиденный вызов метода. Например, перед вызовом этого метода не был вызван метод [IBCPSession::BCPInit](ibcpsession-bcpinit-ole-db.md).  
  
## <a name="see-also"></a>См. также:  
 [IBCPSession &#40;OLE DB&#41;](ibcpsession-ole-db.md)   
 [Выполнение операций массового копирования](../native-client/features/performing-bulk-copy-operations.md)  
  
  
