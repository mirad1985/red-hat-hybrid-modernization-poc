# POC Success Criteria

The goal of this POC is to prove that the proposed setup actually works for the problems Unreal Logistics is trying to solve.

I would consider the POC successful if I can show the following:

## RHEL automation

AAP can connect to the RHEL 9 VM and run Ansible automation successfully.

I should be able to use that automation to configure the server instead of doing everything manually.

## Repeatable configuration

After the server is configured correctly, running the same Ansible automation again should not keep making unnecessary changes.

I want the second run to show something close to:

```text
changed=0
failed=0
