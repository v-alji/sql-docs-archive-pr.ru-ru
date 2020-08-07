---
title: Настройка поведения средств разбиения текста на слова с помощью пользовательского словаря | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
ms.assetid: a8e278d1-aeaa-48f1-a0c6-5de232c983e4
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 9fb02a47da20134925d9b2486ea0c08091af4aa6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732533"
---
# <a name="customize-the-behavior-of-word-breakers-with-a-custom-dictionary"></a><span data-ttu-id="1784c-102">Настройка поведения средств разбиения по словам при работе с пользовательским словарем</span><span class="sxs-lookup"><span data-stu-id="1784c-102">Customize the Behavior of Word Breakers with a Custom Dictionary</span></span>
  <span data-ttu-id="1784c-103">Можно настроить работу средства разбиения по словам для определенного языка, создав для этого языка собственный файл словаря.</span><span class="sxs-lookup"><span data-stu-id="1784c-103">You can customize the behavior of the word breaker for a particular language by creating a language-specific custom dictionary file.</span></span> <span data-ttu-id="1784c-104">Например, можно запретить средству разбиения по словам разбивать определенные термины или фразы.</span><span class="sxs-lookup"><span data-stu-id="1784c-104">For example, you can prevent the word breaker from breaking certain terms or patterns.</span></span>  
  
 <span data-ttu-id="1784c-105">Дополнительные сведения см. в следующей статье SharePoint:</span><span class="sxs-lookup"><span data-stu-id="1784c-105">For more information, see the following SharePoint article:</span></span>  
  
 [<span data-ttu-id="1784c-106">Создание пользовательского словаря (SharePoint Server 2010)</span><span class="sxs-lookup"><span data-stu-id="1784c-106">Create a custom dictionary (SharePoint Server 2010)</span></span>](https://go.microsoft.com/fwlink/?LinkId=215011)  
  
 <span data-ttu-id="1784c-107">В [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]файл пользовательского словаря должен быть размещен в следующей папке:</span><span class="sxs-lookup"><span data-stu-id="1784c-107">For [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], place custom dictionary files in the following folder:</span></span>  
  
 `C:\Program Files\Microsoft SQL Server\<instance name>\MSSQL\Binn`  
  
 <span data-ttu-id="1784c-108">После создания или изменения собственных файлов словарей перезапустите средство запуска управляющей программы полнотекстовой фильтрации SQL Server следующей командой:</span><span class="sxs-lookup"><span data-stu-id="1784c-108">After creating or changing custom dictionary files, restart the SQL Full-text Daemon Launcher with the following command:</span></span>  
  
 `exec sp_fulltext_service 'restart_all_fdhosts'`  
  
  
