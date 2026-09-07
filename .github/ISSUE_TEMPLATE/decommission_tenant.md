name: Decommission of an Existing Tenant
description: Template for standard tenant decommission
title: "[Tenant]: " 
labels: ["architecture" ] 
body: 
  - type: markdown 
    attributes: 
      value: | 
        This issue is for decommission of an existing Tenant within the IAIC infrastructure. 
  - type: input 
    id: tenant-id 
    attributes: 
      label: ID / Tenant name
      placeholder: 
    validations: 
      required: true   
on:
  issues:
    types: [opened]

jobs:
  generate-sub-issues:
    runs-on: ubuntu-latest
    permissions:
      issues: write

    steps:
      - name: Spawn Sub-Issues with Custom Descriptions
        env:
          GH_TOKEN: ${{ secrets.GITHUB_TOKEN }}
          PARENT_ISSUE: ${{ github.event.issue.number }}
          REPO: ${{ github.repository }}
        run: |
          # -----------------------------------------------------------------
          # SUB-ISSUE 1: Move RTX/DGX from Customer Tenant to default Tenant
          # -----------------------------------------------------------------
          gh issue create \
            --repo "$REPO" \
            --parent "$PARENT_ISSUE" \
            --title "⚙️ Move RTX to Default Tenant + Remove VLAN Tagging on each unused port" \
            --label "backend,enhancement" \
            --body "### Technical Description
          Move RTX to Default Tenant + Remove VLAN Tagging on each unused port. #$PARENT_ISSUE.
          
          #### Key Deliverables:
          - [ ] Design and apply the relational database migrations.
          - [ ] Construct REST/GraphQL CRUD endpoints under authenticated routes.
          - [ ] Achieve >80% code coverage via unit tests."

          # ----------------------------------------------------
          # SUB-ISSUE 2: FRONTEND INTEGRATION
          # ----------------------------------------------------
          gh issue create \
            --repo "$REPO" \
            --parent "$PARENT_ISSUE" \
            --title "🎨 Frontend: UI Components & User Flow" \
            --label "frontend,enhancement" \
            --body "### Technical Description
          This issue handles the user interface integration for the parent Epic #$PARENT_ISSUE.
          
          #### Key Deliverables:
          - [ ] Map out the layout inside the application following the design specs.
          - [ ] Bind state management patterns to the new backend API endpoints.
          - [ ] Account for client-side loading states and API fault exceptions."
