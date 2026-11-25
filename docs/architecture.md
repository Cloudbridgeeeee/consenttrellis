# ConsentTrellis — proposed AWS architecture

ConsentTrellis uses AWS to read and organise compliance documents, compare versions accurately and keep a tamper-evident record of every change.

## Request flow

1. Policies & records
2. Amazon S3
3. Textract
4. Bedrock
5. Owner review
6. DynamoDB
7. Evidence pack

## Services

### Amazon Bedrock

**Role:** Classify and compare policies

Classifies policies by family and scope, compares versions clause by clause and drafts plain-language change summaries for approvers to review.

### Amazon Textract

**Role:** Read policies and certificates

Extracts text and structure from policy documents and scanned training certificates, so every record becomes searchable and linkable.

### Amazon S3

**Role:** Store documents and evidence

Keeps every policy version and evidence file encrypted, versioned and protected against accidental deletion.

### Amazon DynamoDB

**Role:** Track owners, reviews and training

Stores policy metadata, owners, review schedules, training links and the audit trail for fast queries and evidence packs.

### AWS Lambda

**Role:** Run reminders and workflows

Sends review reminders, routes changes for approval and assembles evidence packs on request.

## Principles

- **Approved content only** — We organise the policies you approve; we don’t write policy for you.
- **Every change traced** — Versions and approvals form a complete history.
- **Confidential by design** — Documents are encrypted and isolated per organisation.

## Safeguards

- **Not legal advice** — ConsentTrellis organises your compliance work; legal judgements stay with your advisers.
- **Approvers sign off** — No policy version is published without a named approver.
- **Tamper-evident history** — Every change, review and approval is recorded.
- **Staff data protected** — Training records are access-controlled and encrypted.

## MVP scope

Upload your current policies and recent training records. We organise them, set review cycles with your compliance lead, and run your first review and evidence pack together.

- Policy upload and classification
- Version comparison
- Owners and review schedules
- Review reminders
- First audit evidence pack
