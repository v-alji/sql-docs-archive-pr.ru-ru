---
title: MSSQLSERVER_7915 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7915 (Database Engine error)
ms.assetid: 63338587-7dd3-40e6-b70e-d8ae18fff47b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e1dc7a69023e49b48a10da9f0388cbd72fbe46be
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664930"
---
# <a name="mssqlserver_7915"></a>MSSQLSERVER_7915
    
## <a name="details"></a>Сведения  
  
|||  
|-|-|  
|Название продукта|SQL Server|  
|Идентификатор события|7915|  
|Источник события|MSSQLSERVER|  
|Компонент|SQLEngine|  
|Символическое имя|DBCC2_REPAIR_IAM_CHAIN_REBUILT|  
|Текст сообщения|Исправление: последовательность IAM для объекта с идентификатором O_ID, идентификатором индекса I_ID, идентификатором секции PN_ID, идентификатором единицы распределения A_ID (тип TYPE) была усечена до страницы P_ID и будет перестроена.|  
  
## <a name="explanation"></a>Объяснение  
 Это информационное сообщение, отправляемое командой REPAIR, указывает на то, что определенная цепочка карты распределения индекса (IAM) была обновлена, поэтому ее можно перестроить. Для этого обновления, возможно, потребуется размещение нового заголовка IAM-цепочки или удаление из цепочки испорченных страниц.  
  
## <a name="user-action"></a>Действие пользователя  
 None  
  
  
