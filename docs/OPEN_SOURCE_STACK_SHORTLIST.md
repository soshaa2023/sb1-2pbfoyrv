# TINO — Open-Source Reuse Shortlist
Date: 2026-11-04

## Decision
Reuse mature components; do not clone a whole platform because it has many stars. For TINO's first MVP, build a small, secure application for business requests, specialist profiles, admin review, and manual matching. Integrate larger projects only when a concrete need justifies them.

## Shortlist

| Project | What it provides | TINO fit | License / caution | Decision |
|---|---|---|---|---|
| n8n-io/n8n | Workflow automation and integrations | Later: notifications, lead routing, internal operations | Sustainable Use / fair-code, not OSI open source; commercial hosting/reselling restrictions must be checked | Evaluate for internal automation, not core product |
| langgenius/dify | LLM apps, RAG, agent workflows and model/tool management | Later: AI assistants, knowledge-base Q&A, specialist demos | Dify Open Source License is Apache-2.0-based with extra conditions; multi-tenant SaaS requires written authorization and branding restrictions apply | Do not embed as multi-tenant SaaS without licensing clearance |
| OpenHands/OpenHands | AI software-development agent | Potential coding assistant for development | Verify current license, deployment/security model, model/API costs and GitHub permissions before use | Trial in isolated test repo only |
| browser-use/browser-use | Browser automation for agents | Later: carefully scoped admin/research automation | Browser actions can be risky; isolate credentials and require human approval for external actions | Not needed for MVP |
| medusajs/medusa | Commerce backend and commerce modules | Possible future product/catalog commerce | Review current license and enterprise-only directories; likely excessive for service-request MVP | Defer |
| saleor/saleor | Headless commerce API, catalog/orders | Possible future commerce vertical | BSD-3-Clause per repository; operational complexity; check all dependencies | Defer |
| ros-navigation/navigation2 | ROS 2 navigation stack for mobile robots | Robotics service work when customer hardware uses ROS 2 | Package-level licenses vary; check each package and robot/vendor compatibility | Keep as robotics technical reference |
| moveit/moveit2 | ROS 2 motion planning/manipulation | Industrial arms and manipulation projects | BSD-3-Clause repository; hardware drivers and dependencies have their own terms | Keep as robotics technical reference |
| anthropics/claude-code | Agentic coding tool | Developer workflow if a paid/eligible account is available | Product usage may require paid model access; repository presence does not make service free | Optional, not a dependency |

## First implementation recommendation
1. Keep the current TINO app small: public landing page + request form + specialist form + authenticated admin review.
2. Use a conventional backend and PostgreSQL database; do not make Dify, n8n, Medusa, or Saleor the core data layer.
3. Add n8n only after repeatable workflow automation is needed.
4. Add Dify only for a specific AI workflow after licensing and tenant-isolation review.
5. For robotics, do not assume ROS 2 fits every robot. First identify make/model, controller, vendor SDK, safety interfaces, and warranty obligations. Nav2 is for navigation; MoveIt 2 is for manipulation planning—not universal robot repair software.
6. Before adopting any repository: inspect LICENSE, SECURITY.md, releases, recent commits, open critical issues, dependency health, deployment requirements, data flows, and whether it can be maintained by our team.

## Star-count caveat
GitHub stars are a discovery signal, not proof of security, quality, commercial freedom, or suitability. Counts change constantly; validate current repository metadata before making an adoption decision.

## Sources
- https://github.com/n8n-io/n8n
- https://github.com/langgenius/dify
- https://github.com/OpenHands/OpenHands
- https://github.com/browser-use/browser-use
- https://github.com/medusajs/medusa
- https://github.com/saleor/saleor
- https://github.com/ros-navigation/navigation2
- https://github.com/moveit/moveit2
- https://github.com/anthropics/claude-code
