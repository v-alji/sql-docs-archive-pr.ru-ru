---
title: Диалоговое окно "Импорт политик" | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.dmf.importpolicy.f1
ms.assetid: 78ab5f6e-2f13-4788-937e-8892ef4e2345
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2601c21ea08d00bf77e9b97a5186f2d6d1200a10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655695"
---
# <a name="import-policies-dialog-box"></a>Диалоговое окно «Импорт политик»
  Это диалоговое окно используется для импорта одной или нескольких политик (и упоминаемого в них условия), сохраненных в виде XML-файлов, в текущий экземпляр компонента [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] .  
  
## <a name="options"></a>Параметры  
 **Файлы, подлежащие импорту**  
 Чтобы выполнить импорт политики из XML-файла, введите путь и имя файла или нажмите кнопку "Обзор" ( **...** ).  
  
 **Заменять дубликаты импортируемыми элементами**  
 Выберите, чтобы перезаписать любую существующую политику или условие с тем же именем, если они уже существуют в экземпляре компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] . Перезаписать условие с зависимой политикой можно только в том случае, если зависимая политика также переписывается. Если данный параметр не выбран, то наличие условия с таким же выражением не вызовет ошибку.  
  
 **Состояние политики**  
 Выберите требуемое состояние для импортированной политики:  
  
-   **Сохранить состояние политики при импорте**  
  
-   **Включить все политики при импорте**  
  
-   **Выключить все политики при импорте**  
  
## <a name="see-also"></a>См. также:  
 [Администрирование серверов с помощью управления на основе политик](administer-servers-by-using-policy-based-management.md)   
 [Импорт политики управления на основе политик](import-a-policy-based-management-policy.md)   
 [Экспорт политики управления на основе политик](export-a-policy-based-management-policy.md)  
  
  