---
title: "How to: Project Query Results (WCF Data Services) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-oob"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "projection [WCF Data Services]"
  - "WCF Data Services, projection"
  - "query projection [WCF Data Services]"
  - "WCF Data Services, querying"
ms.assetid: 474ac625-8770-43ba-8320-d3315ea9530f
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
---
# How to: Project Query Results (WCF Data Services)
Projection provides a mechanism to reduce the amount of data returned by a query by specifying that only certain properties of an entity are returned in the response. You can perform projections on the results of an [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] query either by using the `$select` query option or by using the [select](~/docs/csharp/language-reference/keywords/select-clause.md) clause ([Select](~/docs/visual-basic/language-reference/queries/select-clause.md) in Visual Basic) in a LINQ query. For more information, see [Querying the Data Service](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md).  
  
 The example in this topic uses the Northwind sample data service and autogenerated client data service classes. This service and the client data classes are created when you complete the [WCF Data Services quickstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
## Example  
 The following example shows a LINQ query that projects Customers entities into a new CustomerAddress type, which contains only address-specific properties plus the identity property. This `CustomerAddress` class is defined on the client and is attributed so that the client library can recognize it as an entity type.  
  
 [!code-csharp[Astoria Northwind Client#SelectCustomerAddress](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#selectcustomeraddress)]
 [!code-vb[Astoria Northwind Client#SelectCustomerAddress](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#selectcustomeraddress)]  
  
## Example  
 The following example shows a LINQ query that projects returned Customers entities into a new CustomerAddressNonEntity type, which contains only address-specific properties and no identity property. This `CustomerAddressNonEntity` class is defined on the client and is not attributed as an entity type.  
  
 [!code-csharp[Astoria Northwind Client#SelectCustomerAddressNonEntity](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#selectcustomeraddressnonentity)]
 [!code-vb[Astoria Northwind Client#SelectCustomerAddressNonEntity](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#selectcustomeraddressnonentity)]  
  
## Example  
 The following example shows the definitions of the `CustomerAddress``CustomerAddressNonEntity` types that are used in the previous examples.  
  
 [!code-csharp[Astoria Northwind Client#CustomerAddressDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/customeraddress.cs#customeraddressdefinition)]
 [!code-vb[Astoria Northwind Client#CustomerAddressDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customeraddress.vb#customeraddressdefinition)]