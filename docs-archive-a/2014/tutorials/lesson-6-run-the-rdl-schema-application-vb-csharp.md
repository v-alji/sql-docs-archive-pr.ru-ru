---
title: 'Занятие 6. Запуск приложения схемы языка определения отчетов (VB-C #) | Документация Майкрософт'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: a2cd2386-2df8-4b69-ab81-9ad1a31f6d27
author: markingmyname
ms.author: maghan
manager: kfile
ms.openlocfilehash: 5a0fc2cd9c12b4b1602f517dc215ca44e686c663
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727490"
---
# <a name="lesson-6-run-the-rdl-schema-application-vb-c"></a>Занятие 6. Запуск приложения схемы языка определения отчетов (VB-C #)
  В среде [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] доступно два способа построения и выполнения приложения командной строки из интегрированной среды разработки:  
  
-   запустить (с отладкой);  
  
-   запустить без отладки.  
  
### <a name="to-build-and-run-the-samplerdlschema-application"></a>Сборка и запуск приложения SampleRDLSchema  
  
1.  В меню **Отладка** выберите команду **Запуск без отладки**. При выборе этой команды окно консоли останется открытым после того, как программа завершит свою работу.  
  
     Приложение выводит на консоль следующие данные:  
  
    ```  
    Loading Report Definition  
    Updating Report Definition  
    - Old Description: <Old Report Description>  
    - New Description: <New Report Description>  
    Publishing Report Definition  
    ```  
  
2.  Чтобы закрыть консоль, нажмите любую кнопку.  
  
    > [!NOTE]  
    >  Сведения обо всех возникающих ошибках выводятся на консоль.  
  
3.  Когда образец приложения закончит выполнение, на сервере отчетов будет сохранена обновленная копия отчета.  
  
## <a name="see-also"></a>См. также:  
 [Обновление отчетов с использованием классов, созданных из учебника по схеме языка определения отчетов &#40;SSRS&#41;](../../2014/tutorials/updating-reports-using-classes-generated-from-the-rdl-schema-ssrs-tutorial.md)   
 [Язык определения отчетов (службы SSRS)](../reporting-services/reports/report-definition-language-ssrs.md)  
  
  
