cat > README.md <<'EOF'
# AWS Cloud Threat Detection & Incident Response Lab

## Overview

This lab demonstrates a controlled AWS cloud security monitoring and incident-response workflow using AWS-native security services.

The exercise covers:

- CloudTrail activity logging
- IAM identity investigation
- Amazon GuardDuty threat detection
- AWS Security Hub finding centralization
- Credential containment
- Persistence analysis
- Incident remediation

## Architecture

```text
                    AWS Organization
                           │
            ┌──────────────┴──────────────┐
            │                             │
     Management Account            Security Account
            │                    GuardDuty + Security Hub
            │                             │
            └──────────────┐              │
                           ▼              │
                      Dev Account         │
                           │              │
                  incident-response-test │
                           │              │
                           ▼              │
                       CloudTrail         │
                           │              │
                           └──────────────┘
                                  │
                                  ▼
                         Detection & Response
