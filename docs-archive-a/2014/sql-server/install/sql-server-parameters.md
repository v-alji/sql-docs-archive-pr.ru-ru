---
title: Параметры SQL Server | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Database Engine analysis [Upgrade Advisor]
- SQL Server Upgrade Advisor, Database Engine
- Upgrade Advisor [SQL Server], Database Engine
- analyzing system [Upgrade Advisor], Database Engine
ms.assetid: 44a18bfe-e593-47a5-995f-382c01d3f618
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 2b885e7616506fd08cae99166cc794dbfb5dac7d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735846"
---
# <a name="sql-server-parameters"></a>Параметры SQL Server
  На этой странице можно установить параметры, которые будут использованы для анализа компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)]. Можно выполнить анализ одной, нескольких или всех баз данных, проанализировать файлы трассировки, созданные программой [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], и пакетные файлы SQL.  
  
> [!NOTE]  
>  Некоторые проблемы обновления можно обнаружить только с помощью анализа файлов трассировки или пакетных файлов SQL.  
  
## <a name="options"></a>Варианты  
 **Базы данных для анализа**  
 Чтобы проанализировать все базы данных, установите флажок **все базы данных** . Чтобы выполнить анализ выбранных баз данных, установите флажок рядом с каждой просматриваемой базой данной.  
  
 **Анализировать файлы трассировки**  
 Установите этот флажок, чтобы выполнить анализ файлов трассировки в файловой системе.  
  
 **Путь к файлам трассировки**  
 Можно выполнить анализ одного или нескольких файлов. Можно выполнить обзор и выбрать несколько файлов или же задать несколько имен файлов. Для каждого файла следует указывать полный путь, включая имя файла. Отдельные записи разделяются символом вертикальной черты (|).  
  
 Если включить **Анализ файлов трассировки**, **следующее** будет отключено до тех пор, пока не будет введен путь и имя файла.  
  
 **Анализ [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] пакетных файлов**  
 Установите этот флажок, чтобы выполнить анализ пакетных файлов [!INCLUDE[tsql](../../includes/tsql-md.md)] в файловой системе.  
  
 **Путь к [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] пакетным файлам**  
 Можно выполнить анализ одного или нескольких пакетных файлов. Можно выполнить обзор и выбрать несколько файлов или же задать несколько имен файлов. Для каждого файла следует указывать полный путь, включая имя файла. Отдельные записи разделяются символом вертикальной черты (|).  
  
 Если включить **анализ пакетных файлов SQL**, кнопка **Далее** будет неактивна, пока не будет введен путь и имя файла.  
  
 **Разделитель пакетов SQL**  
 Текст, используемый для разделения пакетов инструкций [!INCLUDE[tsql](../../includes/tsql-md.md)]. Значение по умолчанию — **Go**.  
  
## <a name="see-also"></a>См. также:  
 [Работа с советником по переходу](../../../2014/sql-server/install/working-with-upgrade-advisor.md)   
 [Справочник по пользовательскому интерфейсу помощника по обновлению](../../../2014/sql-server/install/upgrade-advisor-user-interface-reference.md)  
  
  