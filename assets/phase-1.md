# Phase 1: Scope & Specification

## Project Name

**GrowBot** – A Telegram Community Growth Platform

---

# 1. Vision

GrowBot is a platform designed to help Telegram community owners grow their groups and channels organically through referral campaigns, automated invite attribution, and actionable analytics.

Rather than relying on manual invite contests or multiple bots, GrowBot provides a complete growth solution consisting of:

* **Telegram Bot** – Integrates with Telegram, manages communities, receives updates, and sends notifications.
* **Telegram Mini App** – Handles user authentication, referral attribution, and campaign participation.
* **Web Dashboard** – The primary interface for administrators to manage campaigns, communities, and analytics.

The long-term vision is to become a comprehensive growth platform for Telegram communities while maintaining a simple user experience.

---

# 2. Problem Statement

Telegram provides excellent communication tools but lacks built-in features for community growth and referral marketing.

Community owners currently struggle with:

* Manually tracking invite campaigns.
* Verifying who invited whom.
* Rewarding members fairly.
* Measuring campaign performance.
* Understanding community growth trends.

Existing solutions typically solve only one part of the problem, requiring administrators to use multiple bots and external tools.

GrowBot centralizes referral management, campaign administration, and analytics into a single platform.

---

# 3. Project Goals

## Primary Goal

Develop a Minimum Viable Product (MVP) that enables Telegram community administrators to create, manage, and monitor referral campaigns through a web dashboard while automating referral attribution using a Telegram Mini App.

## Secondary Goals

* Encourage organic community growth.
* Eliminate manual referral tracking.
* Simplify campaign management.
* Provide reliable referral attribution.
* Build a scalable architecture for future premium features.

---

# 4. Target Users

## Primary Users

* Telegram Group Owners
* Telegram Channel Owners
* Community Managers

## Secondary Users

* Course Creators
* Crypto Communities
* Gaming Communities
* Content Creators
* Businesses using Telegram communities
* Startup communities

---

# 5. Product Components

The MVP consists of three major components.

## Telegram Bot

Responsible for:

* Community registration
* Receiving Telegram webhook events
* Tracking member joins and leaves
* Sending campaign notifications
* Synchronizing community data

---

## Telegram Mini App

Responsible for:

* User authentication using Telegram
* Referral attribution
* Campaign participation
* Secure referral verification
* Redirecting users into communities

---

## Web Dashboard

Responsible for:

* Campaign management
* Community management
* Analytics
* Leaderboards
* Referral monitoring
* Administrative configuration

The dashboard is the primary interface for administrators.

---

# 6. MVP Scope

The MVP focuses on validating GrowBot's core value proposition: **automated referral campaigns for Telegram communities.**

## Included Features

### Authentication

* Telegram Login
* Secure session management
* JWT authentication
* Community ownership verification

---

### Workspace Management

An administrator can manage multiple Telegram communities from a single account.

Future subscription plans may define limits such as:

* Maximum communities
* Maximum campaigns
* Analytics retention
* Export limits

For the MVP, these limits are configurable by the system.

---

### Community Registration

Administrators can:

* Add GrowBot to a Telegram group or channel.
* Register the community.
* Configure required permissions.
* Connect the community to the dashboard.

---

### Referral Campaign Management

Administrators can create multiple campaigns for each community.

Campaign configuration includes:

* Campaign title
* Description
* Referral target
* Reward description
* Start date
* End date
* Campaign status
* Referral validation rules

Example:

> Invite 5 friends and receive VIP access.

---

### Referral Attribution

Instead of relying solely on Telegram invite links, GrowBot attributes referrals through the Telegram Mini App.

Referral flow:

1. Participant shares a GrowBot referral link.
2. Invitee opens the Telegram Mini App.
3. Telegram authenticates the user automatically.
4. GrowBot stores a temporary referral intent.
5. User joins the Telegram community.
6. Telegram webhook verifies the membership.
7. Referral is permanently recorded.

This approach provides reliable attribution while minimizing Bot API limitations.

---

### Configurable Referral Validation

Community administrators can define when a referral becomes valid.

Examples include:

* Immediately after joining.
* After remaining in the community for a configurable period.
* After sending at least one message (groups only).

These validation rules allow communities to discourage fake referrals.

---

### Progress Tracking

Participants can:

* View active campaigns
* Monitor referral progress
* View earned rewards
* Participate in multiple campaigns across multiple communities

Example:

```
Community:
AI Community

Campaign:
Invite 5 Friends

Progress:
3 / 5

Reward:
VIP Access
```

---

### Reward Management

Rewards are defined entirely by the administrator.

GrowBot only tracks reward status.

Example statuses include:

* Pending
* Approved
* Delivered
* Rejected

Reward fulfillment remains manual during the MVP.

---

### Analytics Dashboard

Administrators can monitor:

* Community growth
* Referral conversions
* Active campaigns
* Top inviters
* Daily member growth
* Campaign performance

---

### Leaderboards

Campaign leaderboards display members ranked by successful referrals.

Leaderboards encourage competition and community engagement.

---

### Reporting

Administrators can export referral and campaign data for external reporting and analysis.

---

# 7. Out of Scope (Future Releases)

The following features are intentionally excluded from Phase 1:

* AI growth recommendations
* Automated reward fulfillment
* Subscription billing
* Team management
* Public API
* Mobile applications
* Discord integration
* WhatsApp integration
* Enterprise administration
* Advanced fraud detection
* Marketing automation

---

# 8. Functional Requirements

## Administrator

Administrators shall be able to:

* Register communities.
* Connect Telegram groups and channels.
* Manage multiple communities.
* Create multiple referral campaigns.
* Configure campaign validation rules.
* View analytics.
* Export campaign data.
* Manage reward statuses.
* View leaderboards.
* Pause or terminate campaigns.

---

## Community Members

Members shall be able to:

* Join campaigns.
* Receive referral links.
* Participate in campaigns across multiple communities.
* Track referral progress.
* View rankings.
* Receive campaign updates.

---

## Telegram Bot

The bot shall:

* Process Telegram webhook events.
* Detect joins and leaves.
* Synchronize community membership.
* Notify users and administrators.
* Maintain campaign synchronization.

---

## Telegram Mini App

The Mini App shall:

* Authenticate users securely.
* Register referral intent.
* Redirect users into communities.
* Display campaign information.
* Track user participation.

---

# 9. Non-Functional Requirements

## Performance

* Dashboard pages should load within two seconds.
* Telegram bot responses should be under one second.
* Referral verification should occur in near real time.

---

## Scalability

The architecture should support:

* Hundreds of communities.
* Thousands of active campaigns.
* Tens of thousands of tracked referrals.

The system should allow future horizontal scaling.

---

## Availability

Target platform availability:

**99% uptime**

---

## Security

The system shall implement:

* HTTPS
* Telegram authentication verification
* JWT authentication
* Role-based authorization
* Input validation
* Rate limiting
* Secure credential storage
* Webhook verification

---

# 10. Technology Stack

## Frontend

* Next.js
* React
* TypeScript
* Tailwind CSS
* shadcn/ui
* TanStack Query
* Recharts

---

## Backend

* NestJS
* TypeScript
* Prisma ORM

---

## Database

* PostgreSQL

---

## Cache & Temporary Storage

* Redis

Used for:

* Temporary referral intents
* Session caching
* Rate limiting
* Background processing

---

## Telegram Integration

* Telegram Bot API
* Telegram Mini Apps
* grammY (preferred framework)

---

## Authentication

* Telegram Login
* Telegram Mini App authentication
* JWT

---

## Infrastructure

* Docker
* Docker Compose
* Nginx
* GitHub Actions
* VPS deployment (Hetzner or DigitalOcean)

---

## Monitoring

* Sentry
* Prometheus
* Grafana
* Pino or Winston logging

---

# 11. MVP Deliverables

## Backend

* Telegram Bot
* Telegram webhook integration
* REST API
* Authentication
* Referral attribution service
* Campaign management service
* Analytics service

---

## Frontend

* Administrator dashboard
* Authentication
* Community management
* Campaign management
* Analytics dashboard
* Leaderboards
* Settings

---

## Telegram Mini App

* User authentication
* Referral registration
* Campaign participation
* Progress tracking

---

## Database

* PostgreSQL schema
* Prisma migrations
* Seed data

---

## Infrastructure

* Dockerized deployment
* Production configuration
* CI/CD pipeline
* Documentation

---


# 12. Success Criteria

The MVP will be considered successful if it can:

* Allow administrators to manage multiple Telegram communities from a single account.
* Support both Telegram **groups** and **channels**.
* Enable administrators to create and manage multiple referral campaigns.
* Reliably attribute referrals using the Telegram Mini App and webhook verification flow.
* Allow members to participate in campaigns across multiple communities.
* Provide configurable referral validation rules.
* Display real-time campaign progress and leaderboards.
* Provide administrators with actionable analytics through the web dashboard.
* Export campaign data for reporting.
* Support at least **100 communities**, **1,000 active campaigns**, and **10,000 verified referrals** while maintaining reliable performance.

---

## Phase 1 Outcome

At the end of Phase 1, GrowBot should deliver a production-ready MVP that proves its core value proposition: **making Telegram community growth measurable, automated, and fair through referral campaigns powered by a Telegram Bot, Mini App, and web dashboard.** This foundation will support future enhancements such as subscription plans, AI-powered growth insights, advanced anti-fraud mechanisms, automated rewards, and multi-platform integrations without requiring major architectural changes.
