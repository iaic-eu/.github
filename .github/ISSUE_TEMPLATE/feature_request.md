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
	label: ID / Názov Tenanta 
	placeholder: 
	validations: 
	required: true   
  - type: textarea 
	id: infrastructure-notes 
	attributes: 
		label: Technické poznámky (IP rozsahy, špecifikácie) 
		placeholder: Zadajte požadované sieťové segmenty, typy inštancií atď. 
  - type: textarea 
	id: subtasks 
	attributes: 
		label: Kroky pre zriadenie tenanta (Sub-issues) 
		description: Tieto položky po vytvorení issue premeňte kliknutím na natívne sub-issues. 
		value: | 
			- [ ] Fill VPN Fact Sheet 
			- [ ] Configure Tenant TAN 
			- [ ] Configure Tenant VPN 
			- [ ] Allocate DGX/RTX 
			- [ ] Configure IB/RoCE Network 
			- [ ] Confirm VPN Connectivity 
			- [ ] Update Netbox Values for Tenant 
