---
title: Реализация политики подписывания путем задания значения реестра | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- signing policies [Integration Services]
ms.assetid: 64f6966f-2292-401f-acb1-2ccb5aee484a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1e844b65df5b45f212554f7583f4e4b327b740e0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655836"
---
# <a name="implement-a-signing-policy-by-setting-a-registry-value"></a><span data-ttu-id="fb0d9-102">Реализация политики подписывания путем задания параметра реестра</span><span class="sxs-lookup"><span data-stu-id="fb0d9-102">Implement a Signing Policy by Setting a Registry Value</span></span>
  <span data-ttu-id="fb0d9-103">Для управления организационной политикой при загрузке подписанных и неподписанных пакетов можно использовать необязательный параметр реестра.</span><span class="sxs-lookup"><span data-stu-id="fb0d9-103">You can use an optional registry value to manage an organization's policy for loading signed or unsigned packages.</span></span> <span data-ttu-id="fb0d9-104">При использовании данного параметра реестра его необходимо создать на каждом компьютере, где будут выполняться пакеты [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] и где требуется принудительное выполнение этой политики.</span><span class="sxs-lookup"><span data-stu-id="fb0d9-104">If you use this registry value, you must create this registry value on each computer on which [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages will run and on which you want to enforce the policy.</span></span> <span data-ttu-id="fb0d9-105">После задания такого параметра реестра службы [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] будут проверять наличие и верность подписи перед загрузкой пакетов.</span><span class="sxs-lookup"><span data-stu-id="fb0d9-105">After the registry value has been set, [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] will check or verify the signatures before loading packages.</span></span>  
  
 <span data-ttu-id="fb0d9-106">Процедура, описанная в этом разделе, позволяет добавить необязательный параметр `BlockedSignatureStates` типа DWORD в раздел реестра «HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\100\SSIS».</span><span class="sxs-lookup"><span data-stu-id="fb0d9-106">This procedure in this topic describes how to add the optional `BlockedSignatureStates` DWORD value to the HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\100\SSIS registry key.</span></span> <span data-ttu-id="fb0d9-107">Значение данных в `BlockedSignatureStates` определяет, должен ли пакет быть заблокирован, если у него ненадежная подпись, недопустимая подпись или он вообще не подписан.</span><span class="sxs-lookup"><span data-stu-id="fb0d9-107">The data value in `BlockedSignatureStates` determines whether a package should be blocked if it has an untrusted signature, has an invalid signature, or is unsigned.</span></span> <span data-ttu-id="fb0d9-108">Что касается состояния подписей, используемых для пакетов, то в значении реестра `BlockedSignatureStates` используются следующие определения:</span><span class="sxs-lookup"><span data-stu-id="fb0d9-108">With regard to the status of signatures used to sign packages, the `BlockedSignatureStates` registry value uses the following definitions:</span></span>  
  
-   <span data-ttu-id="fb0d9-109">*Действительная подпись* — это подпись, которая может быть успешно прочитана.</span><span class="sxs-lookup"><span data-stu-id="fb0d9-109">A *valid signature* is one that can be read successfully.</span></span>  
  
-   <span data-ttu-id="fb0d9-110">*Недействительная подпись* — это подпись, для которой расшифрованная контрольная сумма (односторонний хэш-код пакета, зашифрованного закрытым ключом), не соответствует расшифрованной контрольной сумме, вычисленной в процессе загрузки пакетов служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fb0d9-110">An *invalid signature* is one for which the decrypted checksum (the one-way hash of the package code encrypted by a private key) does not match the decrypted checksum that is calculated as part of the process of loading [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages.</span></span>  
  
-   <span data-ttu-id="fb0d9-111">*Надежная подпись* — это подпись, которая создается с использованием цифрового сертификата, подписанного доверенным центром сертификации.</span><span class="sxs-lookup"><span data-stu-id="fb0d9-111">A *trusted signature* is one that is created by using a digital certificate signed by a Trusted Root Certification Authority.</span></span> <span data-ttu-id="fb0d9-112">При этом не требуется присутствия подписывающей стороны в списке доверенных издателей пользователя.</span><span class="sxs-lookup"><span data-stu-id="fb0d9-112">This setting does not require the signer to be found in the user's list of Trusted Publishers.</span></span>  
  
-   <span data-ttu-id="fb0d9-113">*Ненадежная подпись* — это подпись, которая не может быть подтверждена доверенным центром сертификации, или подпись, которая не является текущей.</span><span class="sxs-lookup"><span data-stu-id="fb0d9-113">An *untrusted signature* is one that cannot be verified as issued by a Trusted Root Certification Authority, or a signature that is not current.</span></span>  
  
 <span data-ttu-id="fb0d9-114">Следующая таблица перечисляет допустимые значения параметра типа DWORD и связанные с ними политики.</span><span class="sxs-lookup"><span data-stu-id="fb0d9-114">The following table lists the valid values of the DWORD data and their associated policy.</span></span>  
  
|<span data-ttu-id="fb0d9-115">Значение</span><span class="sxs-lookup"><span data-stu-id="fb0d9-115">Value</span></span>|<span data-ttu-id="fb0d9-116">Описание</span><span class="sxs-lookup"><span data-stu-id="fb0d9-116">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="fb0d9-117">0</span><span class="sxs-lookup"><span data-stu-id="fb0d9-117">0</span></span>|<span data-ttu-id="fb0d9-118">Нет административного ограничения.</span><span class="sxs-lookup"><span data-stu-id="fb0d9-118">No administrative restriction.</span></span>|  
|<span data-ttu-id="fb0d9-119">1</span><span class="sxs-lookup"><span data-stu-id="fb0d9-119">1</span></span>|<span data-ttu-id="fb0d9-120">Заблокировать недопустимые подписи.</span><span class="sxs-lookup"><span data-stu-id="fb0d9-120">Block invalid signatures.</span></span><br /><br /> <span data-ttu-id="fb0d9-121">Этот параметр не блокирует неподписанные пакеты.</span><span class="sxs-lookup"><span data-stu-id="fb0d9-121">This setting does not block unsigned packages.</span></span>|  
|<span data-ttu-id="fb0d9-122">2</span><span class="sxs-lookup"><span data-stu-id="fb0d9-122">2</span></span>|<span data-ttu-id="fb0d9-123">Заблокировать недопустимые и ненадежные подписи.</span><span class="sxs-lookup"><span data-stu-id="fb0d9-123">Block invalid and untrusted signatures.</span></span><br /><br /> <span data-ttu-id="fb0d9-124">Этот параметр не блокирует неподписанные пакеты, но блокирует самостоятельно сформированные подписи.</span><span class="sxs-lookup"><span data-stu-id="fb0d9-124">This setting does not block unsigned packages, but blocks self-generated signatures.</span></span>|  
|<span data-ttu-id="fb0d9-125">3</span><span class="sxs-lookup"><span data-stu-id="fb0d9-125">3</span></span>|<span data-ttu-id="fb0d9-126">Заблокировать недопустимые и ненадежные подписи и неподписанные пакеты.</span><span class="sxs-lookup"><span data-stu-id="fb0d9-126">Block invalid and untrusted signatures and unsigned packages</span></span><br /><br /> <span data-ttu-id="fb0d9-127">Это параметр также блокирует самостоятельно сформированные подписи.</span><span class="sxs-lookup"><span data-stu-id="fb0d9-127">This setting also blocks self-generated signatures.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="fb0d9-128">Рекомендованное значение для `BlockedSignatureStates` — 3.</span><span class="sxs-lookup"><span data-stu-id="fb0d9-128">The recommended setting for `BlockedSignatureStates` is 3.</span></span> <span data-ttu-id="fb0d9-129">Это обеспечивает наибольшую защиту от неподписанных пакетов или подписей, которые являются либо недействительными, либо ненадежными.</span><span class="sxs-lookup"><span data-stu-id="fb0d9-129">This setting provides the greatest protection against unsigned packages or signatures that are either not valid or untrusted.</span></span> <span data-ttu-id="fb0d9-130">Однако рекомендованное значение не может подходить для всех случаев.</span><span class="sxs-lookup"><span data-stu-id="fb0d9-130">However, the recommended setting may not be appropriate in all circumstances.</span></span> <span data-ttu-id="fb0d9-131">Дополнительные сведения о подписывании электронных ресурсов см. в разделе[Введение в подписывание кода](https://go.microsoft.com/fwlink/?LinkId=51414)библиотеки MSDN.</span><span class="sxs-lookup"><span data-stu-id="fb0d9-131">For more information about signing digital assets, see the topic, "[Introduction to Code Signing](https://go.microsoft.com/fwlink/?LinkId=51414)," in the MSDN Library.</span></span>  
  
### <a name="to-implement-a-signing-policy-for-packages"></a><span data-ttu-id="fb0d9-132">Реализация политики подписи пакетов</span><span class="sxs-lookup"><span data-stu-id="fb0d9-132">To implement a signing policy for packages</span></span>  
  
1.  <span data-ttu-id="fb0d9-133">В меню **Пуск** выберите команду **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="fb0d9-133">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="fb0d9-134">В диалоговом окне Выполнить введите `Regedit` и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="fb0d9-134">In the Run dialog box, type `Regedit`, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="fb0d9-135">Найдите раздел реестра HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\100\SSIS.</span><span class="sxs-lookup"><span data-stu-id="fb0d9-135">Locate the registry key, HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\100\SSIS.</span></span>  
  
4.  <span data-ttu-id="fb0d9-136">Щелкните правой кнопкой мыши раздел **MSDTS**, укажите пункт **Создать**, а затем щелкните **Параметр DWORD**.</span><span class="sxs-lookup"><span data-stu-id="fb0d9-136">Right-click **MSDTS**, point to **New**, and then click **DWORD Value**.</span></span>  
  
5.  <span data-ttu-id="fb0d9-137">Обновите имя нового значения до `BlockedSignatureStates`.</span><span class="sxs-lookup"><span data-stu-id="fb0d9-137">Update the name of the new value to `BlockedSignatureStates`.</span></span>  
  
6.  <span data-ttu-id="fb0d9-138">Щелкните правой кнопкой мыши `BlockedSignatureStates` и выберите пункт **изменить**.</span><span class="sxs-lookup"><span data-stu-id="fb0d9-138">Right-click `BlockedSignatureStates` and click **Modify**.</span></span>  
  
7.  <span data-ttu-id="fb0d9-139">В диалоговом окне **Изменение параметра DWORD** введите значение 0, 1, 2 или 3.</span><span class="sxs-lookup"><span data-stu-id="fb0d9-139">In the **Edit DWORD Value** dialog box, type the value 0, 1, 2, or 3.</span></span>  
  
8.  <span data-ttu-id="fb0d9-140">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="fb0d9-140">Click **OK**.</span></span>  
  
9. <span data-ttu-id="fb0d9-141">В меню **Файл** выберите пункт **Выход**.</span><span class="sxs-lookup"><span data-stu-id="fb0d9-141">On the **File** menu, click **Exit**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb0d9-142">См. также:</span><span class="sxs-lookup"><span data-stu-id="fb0d9-142">See Also</span></span>  
 <span data-ttu-id="fb0d9-143">[Общие сведения о безопасности &#40;Integration Services&#41;](security/security-overview-integration-services.md) </span><span class="sxs-lookup"><span data-stu-id="fb0d9-143">[Security Overview &#40;Integration Services&#41;](security/security-overview-integration-services.md) </span></span>  
 [<span data-ttu-id="fb0d9-144">Определение источника пакетов с помощью цифровых подписей</span><span class="sxs-lookup"><span data-stu-id="fb0d9-144">Identify the Source of Packages with Digital Signatures</span></span>](security/identify-the-source-of-packages-with-digital-signatures.md)  
  
  
