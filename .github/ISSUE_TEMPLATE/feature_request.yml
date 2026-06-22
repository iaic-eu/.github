name: Create a New Tenant 
description: Template for creation of a new Tenant in IAIC infrastructure
title: "[Tenant]: " 
labels: ["architecture" ] 
body: 
  - type: markdown 
	attributes: 
	value: | 
	This issue is for creation of a new Tenant within the IAIC infrastructure. 
  - type: input 
	id: tenant-id 
	attributes: 
	label: ID / Tenant name
	placeholder: 
	validations: 
	required: true   
  - type: textarea 
	id: infrastructure-notes 
	attributes: 
		label: Technical notes
		placeholder: Zadajte požadované sieťové segmenty, typy inštancií atď. 
  - type: textarea 
	id: subtasks 
	attributes: 
		label: Complete subissues necessary for Tenant creation
		description: After creating this issue change to native sub-issues
		value: | 
			- [ ] Fill VPN Fact Sheet 
			- [ ] Configure Tenant TAN 
			- [ ] Configure Tenant VPN 
			- [ ] Allocate DGX/RTX 
			- [ ] Configure IB/RoCE Network 
			- [ ] Confirm VPN Connectivity 
			- [ ] Update Netbox Values for Tenant 
