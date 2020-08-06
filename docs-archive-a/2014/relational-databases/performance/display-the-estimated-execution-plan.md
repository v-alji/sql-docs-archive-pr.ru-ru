---
title: Отображение предполагаемого плана выполнения | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- zoom [SQL Server]
- estimated execution plan [SQL Server]
- displaying execution plans
- viewing execution plans
- execution plans [SQL Server], displaying
- customizing execution plan display [SQL Server]
- modifying execution plan display
- custom zoom [SQL Server]
ms.assetid: e94aa576-4c0c-4c54-ad05-6c3432cc615b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 79c0972661d40eb9e359cf43f7a1f0b1b2ae4b0c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730533"
---
# <a name="display-the-estimated-execution-plan"></a>Отображение предполагаемого плана выполнения
  В этом разделе описано создание графических предполагаемых планов выполнения с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]. При создании расчетных планов выполнения запросы и пакеты [!INCLUDE[tsql](../../includes/tsql-md.md)] не выполняются. Вместо этого созданный план выполнения отображает наиболее вероятный план выполнения запроса, которому следовал бы компонент [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] при реальном выполнении запросов.  
  
 Для использования этой возможности пользователи должны обладать соответствующими разрешениями на запуск запроса [!INCLUDE[tsql](../../includes/tsql-md.md)] , для которого создается графический план выполнения. Кроме того, пользователям должно быть предоставлено разрешение SHOWPLAN для всех баз данных, упоминаемых в запросе.  
  
### <a name="to-display-the-estimated-execution-plan-for-a-query"></a>Отображение предполагаемого плана выполнения запроса  
  
1.  На панели инструментов нажмите кнопку **Запрос к ядру СУБД**. Можно также нажать на панели инструментов кнопку **Открыть файл** , выбрать существующий запрос и, открыв его, просмотреть предполагаемый план выполнения.  
  
2.  Введите запрос, для которого нужно отобразить предполагаемый план выполнения.  
  
3.  В меню **Запрос** выберите **Показать предполагаемый план выполнения** или нажмите на панели инструментов кнопку **Показать предполагаемый план выполнения** . Предполагаемый план выполнения отображается на вкладке **План выполнения** на панели результатов. Для просмотра дополнительных сведений задержите указатель мыши над значками логического и физического оператора и просмотрите описание и свойства оператора в отобразившейся всплывающей подсказке. Также можно просмотреть свойства оператора в окне «Свойства». Если "Свойства" не видны, щелкните оператор правой кнопкой мыши и выберите **Свойства**. Выберите оператор для просмотра его свойств.  
  
4.  Чтобы изменить отображение плана выполнения, щелкните правой кнопкой мыши план выполнения и выберите **Увеличить масштаб**, **Уменьшить масштаб**, **Пользовательский масштаб**или **Масштаб по размеру**. Кнопки**Увеличить масштаб** и **Уменьшить масштаб** позволяют увеличить или уменьшить план выполнения на фиксированную величину. **Настраиваемый масштаб** позволяет определить собственное значение, например масштаб в 80 процентов. При использовании пункта**Масштаб по размеру** план выполнения масштабируется до размеров панели результатов.  
  
  