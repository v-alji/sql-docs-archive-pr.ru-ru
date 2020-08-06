---
title: Использование заметок в пакетах | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- self-documenting packages
- adding annotations
- annotations [Integration Services]
ms.assetid: 48c8ed9a-b10d-490c-9ba7-4b77aa44e3dd
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 27c7df6afd894ea9730027da1d54786ed8397fad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669465"
---
# <a name="use-annotations-in-packages"></a><span data-ttu-id="e1188-102">Использование заметок в пакетах</span><span class="sxs-lookup"><span data-stu-id="e1188-102">Use Annotations in Packages</span></span>
  <span data-ttu-id="e1188-103">Конструктор служб [!INCLUDE[ssIS](../includes/ssis-md.md)] предоставляет заметки, которые можно использовать для обеспечения самодокументируемости пакетов, упрощения их понимания и поддержки.</span><span class="sxs-lookup"><span data-stu-id="e1188-103">The [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer provides annotations, which you can use to make packages self-documenting and easier to understand and maintain.</span></span> <span data-ttu-id="e1188-104">Заметки вы можете добавлять в области конструктора потока управления, потока данных и обработчика событий конструктора [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e1188-104">You can add annotations to the control flow, data flow, and event handler design surfaces of [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="e1188-105">Заметки могут содержать разные типы текста; они полезны при добавлении меток, примечаний и других описательных сведений в пакет.</span><span class="sxs-lookup"><span data-stu-id="e1188-105">The annotations can contain any type of text, and they are useful for adding labels, comments, and other descriptive information to a package.</span></span> <span data-ttu-id="e1188-106">Создание заметок возможно только во время проектирования.</span><span class="sxs-lookup"><span data-stu-id="e1188-106">Annotations are a design-time feature only.</span></span> <span data-ttu-id="e1188-107">Например, они не записываются в журналы.</span><span class="sxs-lookup"><span data-stu-id="e1188-107">For example, they are not written to logs.</span></span>  
  
 <span data-ttu-id="e1188-108">При нажатии клавиши ВВОД текст переносится на следующую строку.</span><span class="sxs-lookup"><span data-stu-id="e1188-108">When you press ENTER, the text wraps to the next line.</span></span> <span data-ttu-id="e1188-109">Размер поля заметки автоматически увеличивается по мере добавления дополнительных строк текста.</span><span class="sxs-lookup"><span data-stu-id="e1188-109">The annotation box automatically increases in size as you add additional lines of text.</span></span> <span data-ttu-id="e1188-110">Заметки пакета сохраняются в виде обычного текста в разделе CDATA файла пакета.</span><span class="sxs-lookup"><span data-stu-id="e1188-110">Package annotations are persisted as clear text in the CDATA section of the package file.</span></span>  
  
 <span data-ttu-id="e1188-111">Дополнительные сведения об изменении формата файла пакета см. в разделе [Формат пакетов служб SSIS](../../2014/integration-services/ssis-package-format.md).</span><span class="sxs-lookup"><span data-stu-id="e1188-111">For more information about changes to the format of the package file, see [SSIS Package Format](../../2014/integration-services/ssis-package-format.md).</span></span>  
  
 <span data-ttu-id="e1188-112">При сохранении пакета конструктор служб [!INCLUDE[ssIS](../includes/ssis-md.md)] сохраняет включенные в пакет заметки.</span><span class="sxs-lookup"><span data-stu-id="e1188-112">When you save the package, [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer saves the annotations in the package.</span></span>  
  
### <a name="to-add-an-annotation-to-a-package"></a><span data-ttu-id="e1188-113">Добавление заметки к пакету</span><span class="sxs-lookup"><span data-stu-id="e1188-113">To add an annotation to a package</span></span>  
  
-   [<span data-ttu-id="e1188-114">Добавление заметки к пакету</span><span class="sxs-lookup"><span data-stu-id="e1188-114">Add an Annotation to a Package</span></span>](../../2014/integration-services/add-an-annotation-to-a-package.md)  
  
  
