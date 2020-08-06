---
title: Рекомендации и ограничения для SQLXML 4,0 | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- SQLXML, about SQLXML
ms.assetid: fe433d30-90a1-421e-85c6-af13294dc18d
author: rothja
ms.author: jroth
ms.openlocfilehash: e020cbf0ac32e4c878b0b74b67e7c9c679d5d178
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654127"
---
# <a name="guidelines-and-limitations-of-sqlxml-40"></a><span data-ttu-id="0430a-102">Рекомендации по использованию SQLXML 4.0 и действующие ограничения</span><span class="sxs-lookup"><span data-stu-id="0430a-102">Guidelines and Limitations of SQLXML 4.0</span></span>
  <span data-ttu-id="0430a-103">При работе с SQLXML 4.0 надлежит помнить следующее.</span><span class="sxs-lookup"><span data-stu-id="0430a-103">Remember the following when working with SQLXML 4.0:</span></span>  
  
-   <span data-ttu-id="0430a-104">XML-документ, возвращаемый в виде результата запроса, не проверяется по схеме сопоставления, сформировавшей этот документ.</span><span class="sxs-lookup"><span data-stu-id="0430a-104">XML returned as a query result is not validated against the mapping schema that generated the XML.</span></span>  
  
-   <span data-ttu-id="0430a-105">SQLXML 4.0 включает независимые и зависимые от версии идентификаторы PROGID.</span><span class="sxs-lookup"><span data-stu-id="0430a-105">SQLXML 4.0 includes version-independent and version-dependent PROGIDs.</span></span> <span data-ttu-id="0430a-106">Рекомендуется, чтобы все рабочие приложения использовали зависимые от версии идентификаторы PROGID.</span><span class="sxs-lookup"><span data-stu-id="0430a-106">It is recommended that all production applications use version-dependent PROGIDs.</span></span> <span data-ttu-id="0430a-107">Это особенно важно, так как SQLXML 4.0 не имеет полной обратной совместимости.</span><span class="sxs-lookup"><span data-stu-id="0430a-107">This is especially important because SQLXML 4.0 is not fully backward compatible.</span></span> <span data-ttu-id="0430a-108">Использование зависимых от версии идентификаторов PROGID защищает от возможных сбоев в работе при установке новых версий.</span><span class="sxs-lookup"><span data-stu-id="0430a-108">Using version dependent PROGIDs protects from possible production failures when you install newer releases.</span></span> <span data-ttu-id="0430a-109">От версии к версии поведение программы может меняться из-за множества причин, например: исправления ошибок, возможных изменений структуры и т. д.</span><span class="sxs-lookup"><span data-stu-id="0430a-109">From release to release, program behavior may change for a variety of reasons, such as bug fixes, possible design changes, and so on.</span></span> <span data-ttu-id="0430a-110">Использование зависимых от версии идентификаторов PROGID защищает от непредвиденных сбоев при установке новых версий.</span><span class="sxs-lookup"><span data-stu-id="0430a-110">Using version-dependent PROGIDs protects from unexpected failure when you install newer releases.</span></span> <span data-ttu-id="0430a-111">При установке новой версии приложение продолжит работу без сбоев, используя зависимые от версии идентификаторы PROGID.</span><span class="sxs-lookup"><span data-stu-id="0430a-111">With version-dependent PROGIDs, when you install a newer release, your application will continue to work without failure.</span></span> <span data-ttu-id="0430a-112">Если в новой версии требуется изменить предыдущие зависимые от версии идентификаторы PROGID на более актуальные, то перед запуском в работу приложение необходимо протестировать.</span><span class="sxs-lookup"><span data-stu-id="0430a-112">If you decide to change the previous version-dependent PROGIDs and use the recent version-dependent PROGIDs in a newer release, you must test your application before putting it into production.</span></span> <span data-ttu-id="0430a-113">Например, приложения, использующие независимые от версии идентификаторы PROGID, в следующем сценарии могут завершиться с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="0430a-113">For example, applications using version-independent PROGIDs may fail in the following scenario:</span></span>  
  
     <span data-ttu-id="0430a-114">Выполняется приложение, использующее SQLXML 4.0 и независимые от версии идентификаторы PROGID, и требуется установить несколько других программ.</span><span class="sxs-lookup"><span data-stu-id="0430a-114">You are running an application that uses SQLXML 4.0 and version-independent PROGIDs, and you decide to install some other software program.</span></span> <span data-ttu-id="0430a-115">Эта программа может установить предыдущую версию SQLXML.</span><span class="sxs-lookup"><span data-stu-id="0430a-115">This program might install an earlier version of SQLXML.</span></span> <span data-ttu-id="0430a-116">Приложение может завершиться с ошибкой, так как независимые от версии идентификаторы PROGID в приложении теперь указывают на предыдущую версию SQLXML, в которой может и не быть функции SQLXML, которую использует приложение.</span><span class="sxs-lookup"><span data-stu-id="0430a-116">Your application may fail because the version-independent PROGIDS in your application now point to the earlier version of SQLXML, which may or may not have the SQLXML feature that your application is using.</span></span>  
  
-   <span data-ttu-id="0430a-117">Если по какой либо причине вы не хотите использовать поставщик SQLXMLOLEDB, а хотите использовать поставщик SQLOLEDB для функций SQLXML, задайте для свойства **версия SQLXML** значение "SQLXML. 4.0".</span><span class="sxs-lookup"><span data-stu-id="0430a-117">If for any reason you don't want to use the SQLXMLOLEDB provider, and instead want to use the SQLOLEDB provider for SQLXML features, set the **SQLXML Version** property to "SQLXML.4.0".</span></span>  
  
  
