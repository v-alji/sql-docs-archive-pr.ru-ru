---
title: Диалоговое окно «сведения об олицетворении» (мастер импорта таблиц) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.impersonationinfo.f1
ms.assetid: bee7eee5-0650-41f1-a372-5076ae97a58c
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5300f8b6106a7f29f51018b4e039c2a8c28aa729
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728926"
---
# <a name="impersonation-information-dialog-box-table-import-wizard"></a><span data-ttu-id="4d16d-102">Диалоговое окно «Сведения об олицетворении» (мастер импорта таблиц)</span><span class="sxs-lookup"><span data-stu-id="4d16d-102">Impersonation Information Dialog Box (Table Import Wizard)</span></span>
  <span data-ttu-id="4d16d-103">Страница **Сведения об олицетворении** служит для указания учетных данных, которые будут использоваться [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] для соединения с источником данных.</span><span class="sxs-lookup"><span data-stu-id="4d16d-103">Use the **Impersonation Information** page to specify the credentials that [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] will use to connect to the data source.</span></span> <span data-ttu-id="4d16d-104">Дополнительные сведения об олицетворении учетных данных см. в разделе [Impersonation &#40;SSAS Tabular&#41;](tabular-models/impersonation-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="4d16d-104">For more information about credentials impersonation, see [Impersonation &#40;SSAS Tabular&#41;](tabular-models/impersonation-ssas-tabular.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="4d16d-105">Варианты</span><span class="sxs-lookup"><span data-stu-id="4d16d-105">Options</span></span>  
 <span data-ttu-id="4d16d-106">**Имя и пароль определенного пользователя Windows**</span><span class="sxs-lookup"><span data-stu-id="4d16d-106">**Specific Windows user name and password**</span></span>  
 <span data-ttu-id="4d16d-107">Выберите этот параметр, чтобы в табличной модели использовались учетные данные безопасности указанной пользовательской учетной записи Windows.</span><span class="sxs-lookup"><span data-stu-id="4d16d-107">Select this option to have the tabular model use the security credentials of a specified Windows user account.</span></span>  
  
 <span data-ttu-id="4d16d-108">**User name**</span><span class="sxs-lookup"><span data-stu-id="4d16d-108">**User name**</span></span>  
 <span data-ttu-id="4d16d-109">Введите требуемые домен и имя пользовательской учетной записи.</span><span class="sxs-lookup"><span data-stu-id="4d16d-109">Type the domain and name of the user account to be used.</span></span> <span data-ttu-id="4d16d-110">Используйте следующий формат:</span><span class="sxs-lookup"><span data-stu-id="4d16d-110">Use the following format:</span></span>  
  
 <span data-ttu-id="4d16d-111">*\<Domain name>* **\\** *\<User account name>*</span><span class="sxs-lookup"><span data-stu-id="4d16d-111">*\<Domain name>* **\\** *\<User account name>*</span></span>  
  
 <span data-ttu-id="4d16d-112">Этот параметр будет включен только в случае выбора параметра **Использовать указанные имя пользователя и пароль** .</span><span class="sxs-lookup"><span data-stu-id="4d16d-112">This option is enabled only if **Use a specific name and password** is selected.</span></span>  
  
 <span data-ttu-id="4d16d-113">**Пароль**</span><span class="sxs-lookup"><span data-stu-id="4d16d-113">**Password**</span></span>  
 <span data-ttu-id="4d16d-114">Введите пароль учетной записи пользователя, которая будет использоваться табличной моделью.</span><span class="sxs-lookup"><span data-stu-id="4d16d-114">Type the password of the user account to be used by the Tabular model.</span></span>  
  
 <span data-ttu-id="4d16d-115">Этот параметр будет включен только в случае выбора параметра **Использовать указанные имя пользователя и пароль** .</span><span class="sxs-lookup"><span data-stu-id="4d16d-115">This option is enabled only if **Use a specific name and password** is selected.</span></span>  
  
 <span data-ttu-id="4d16d-116">**Учетная запись службы**</span><span class="sxs-lookup"><span data-stu-id="4d16d-116">**Service account**</span></span>  
 <span data-ttu-id="4d16d-117">Выберите этот параметр для использования учетных данных безопасности, связанных со службой [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , управляющей моделью.</span><span class="sxs-lookup"><span data-stu-id="4d16d-117">Select this option to use the security credentials associated with the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] service that manages the model.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d16d-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="4d16d-118">See Also</span></span>  
 [<span data-ttu-id="4d16d-119">Олицетворение (табличные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="4d16d-119">Impersonation &#40;SSAS Tabular&#41;</span></span>](tabular-models/impersonation-ssas-tabular.md)  
  
  
