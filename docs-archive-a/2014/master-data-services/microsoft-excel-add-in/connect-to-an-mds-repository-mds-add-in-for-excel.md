---
title: Соединение с репозиторием MDS (надстройка MDS для Excel) | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: 8f427312-4c09-4c8b-b9f9-8b235557a74b
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: c1db0594f07da7ff8a78642e4b2de0eb9e507164
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730794"
---
# <a name="connect-to-an-mds-repository-mds-add-in-for-excel"></a>Соединение с репозиторием MDS (надстройка MDS для Excel)
  В [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)]необходимо установить соединение с репозиторием MDS, прежде чем можно будет загружать или публиковать данные.  
  
## <a name="prerequisites"></a>Предварительные требования  
 Для выполнения этой процедуры:  
  
-   Необходимо иметь разрешение на доступ к функциональной области **Обозреватель** .  
  
### <a name="to-connect-to-an-mds-repository"></a>Соединение с репозиторием MDS  
  
1.  В MDS [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)]на вкладке **Основные данные** в группе **Соединение и загрузка** нажмите стрелку под кнопкой **Соединение** и выберите команду **Управление соединениями**.  
  
2.  В диалоговом окне **Управление соединениями** в разделе **Новое соединение** нажмите кнопку **Создать новое соединение**.  
  
3.  Нажмите кнопку **Создать**.  
  
4.  В диалоговом окне **Добавление нового соединения** в поле **Описание** введите описание соединения. Это соединение будет отображаться при нажатии стрелки кнопки **Соединение** на панели инструментов.  
  
5.  В поле **Адрес сервера MDS** введите URL-адрес веб-приложения [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)], например http://contoso/mds.  
  
    > [!NOTE]  
    >  Следует использовать имя компьютера, а не localhost.  
  
6.  Нажмите кнопку **ОК**. Это имя появится в разделе **Существующие соединения** .  
  
7.  Можно нажать кнопку **Проверка** , чтобы проверить соединение. Будет выдано диалоговое окно подтверждения или сообщение об ошибке. Чтобы закрыть его, нажмите кнопку **ОК** .  
  
8.  Нажмите кнопку **Подключиться**. Отображается панель **Службы Master Data Services** .  
  
## <a name="next-steps"></a>Дальнейшие действия  
  
-   [Загрузка данных из MDS в Excel](export-data-to-excel-from-master-data-services.md)  
  
-   [Фильтровать данные перед загрузкой &#40;надстройка MDS для Excel&#41;](filter-data-before-exporting-mds-add-in-for-excel.md)  
  
## <a name="see-also"></a>См. также:  
 [Соединения (надстройка MDS для Excel)](connections-mds-add-in-for-excel.md)  
  
  
