

This document summarizes the key security implementations and takeaways from a hands-on AWS Cloud Security lab. 

Key Security Domains
1. Identity and Access Management (IAM)

    Permissions Implemented: Granted IAMReadOnlyAccess, which includes actions like iam:GetAccountSummary, iam:ListAccountAliases, and iam:ListAccessKeys.

    Security Impact: Prevents unverified users from being created or passwords from being changed, effectively reducing the attack surface.

    Least Privilege: By using the 'StudentA' user with read-only rights, sensitive resources cannot be deleted and security statuses cannot be modified without administrative oversight.

2. S3 Storage Security

    Public Access Blocks: Acts as a core-level prevention mechanism against accidental data leakage.

    Bucket Policies: Utilizes JSON documents to define specific operations and access rights for S3 storage sources.

3. EC2 and SSRF Mitigation

    Security Groups: Restricted to "My IP" to ensure that even if an attacker gains access, they cannot reach the broader network.

    IMDSv2: Unlike its predecessor, IMDSv2 requires a session token and a PUT request, which could have mitigated the SSRF (Server-Side Request Forgery) path used in the Capital One breach.

4. Logging, Monitoring, and Compliance

Continuous surveillance is prioritized over periodic audits to close the "window of opportunity" where attackers might go undetected.
