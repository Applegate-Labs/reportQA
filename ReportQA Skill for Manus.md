# ReportQA Skill for Manus

The **ReportQA** skill automates the rigorous quality assurance and progress tracking of consulting deliverables. It cross-references a draft report against the accumulated knowledge in a project's Data Room to ensure accuracy, consistency, and completeness.

This skill is designed to synthesize information across the entire consulting workflow, making it an invaluable tool for consultants who need to verify claims against raw data, check draft reports for inconsistencies, and generate comprehensive QA progress reports.

## Features

The ReportQA skill performs a multi-step verification process:

1.  **Pre-flight Data Verification:** Ensures that the necessary project data is accessible to Manus before beginning the QA process.
2.  **Ingestion, Parsing, and Version Diffing:** Reads the draft report, understands its structure, and compares it against previous versions to track resolved action items and new issues.
3.  **Internal Consistency and Visual Data Verification:** Checks for logical flow, internal contradictions, and structural completeness. It also utilizes multimodal vision capabilities to analyze charts and graphs, ensuring they accurately reflect the underlying text.
4.  **Context Retrieval and Cross-Referencing:** Queries the Data Room to extract all requirements and cross-references claims. It traces requirements to ensure they are addressed in the report and verifies data against raw files and transcripts.
5.  **Cross-Source Contradiction Detection:** Evaluates underlying data sources against each other to identify ambiguities in the client's own information, flagging contradictions and assessing their severity.
6.  **Live Web Browsing for Fact-Checking:** Utilizes the Manus browser tool to verify external claims, market sizing data, or industry trends mentioned in the report, adding a layer of real-time external validation.
7.  **Output Generation:** Generates a rigorous QA and progress report, including automated stakeholder follow-up drafts for missing information.

## Supported Data Sources

This skill can cross-reference your draft report against a variety of sources:

*   **Client Email Threads:** Summaries of client communications and requirements (ingested via Mail Manus).
*   **Live Meeting Transcripts:** Action items and transcripts from live catch-up calls (captured via Manus Meeting Minutes).
*   **Virtual Meeting & Expert Call Transcripts:** Historical transcripts or expert interviews uploaded to the project.
*   **Data Rooms & Raw Data:** Heavy datasets, financial models, and confidential client documents.

## Prerequisites & Setup

Before running this skill, ensure your project data is accessible to Manus. Data can be provided in several ways:

1.  **Manus Project Files (Recommended for Cloud Workflows):** Upload files directly into your Manus Project space. Ideal for transcripts and Mail Manus summaries.
2.  **Local Folder Mount (Recommended for Heavy/Sensitive Data):** Attach a local folder containing your data room via the Manus Desktop App. Ideal for heavy data rooms, large Excel models, and confidential documents.
3.  **Manus Connectors (Optional):** Connect external data sources like Google Drive, Notion, etc., depending on where your files are stored.

### Mail Manus Workflow Configuration

To automatically process incoming client communications into structured summaries that the skill can read, configure a Mail Manus workflow email:

1.  Go to **Settings → Mail Manus → Workflow Emails → Create New**.
2.  Set the **Name** to "Consulting Comms Processor" and the **Address** to `project-comms@manus.bot` (or your preference).
3.  Use the following **Custom Instruction**:

> Read this email thread or transcript thoroughly. Generate a structured summary document in Markdown format containing the following sections:
> 1. **Actionable Items for the Report** — What specific tasks, analyses, or sections need to be added or modified in the draft report based on this communication?
> 2. **Pending Client Deliverables** — What information, data, or approvals are we currently waiting for the client to send us?
> 3. **Clarifications Needed** — What ambiguities or questions arose in this thread that we need to clarify with the client or stakeholders next?
> 4. **Executive Summary** — A brief summary of what the client ultimately wants, their key concerns, and the overall direction of the project as dictated by this communication.
> 
> Output this as a clean, professional Markdown file that can be downloaded and saved directly into a project data room.

When you receive a client email, forward it to this address. Download the resulting Markdown summary and save it into your local project folder or upload it to your Manus Project Files.

## Output Format

The skill generates a structured Markdown report containing the following sections:

1.  **Executive Summary:** A high-level assessment of the draft's readiness.
2.  **Confidence Scoring:** Scores for each major section based on how well claims are supported by sources.
3.  **Report Inconsistencies and Errors:** Details of logical flaws, data mismatches, or contradictions found in the draft.
4.  **Cross-Source Contradictions & Warnings:** Instances where underlying data sources contradict each other.
5.  **Requirement Traceability & Action Checklist:** A unified checklist tracking all client requirements and their status in the report.
6.  **Automated Stakeholder Follow-up Drafts:** Drafted emails ready to be sent to stakeholders for missing information or unresolved queries.

## Usage

Once the data sources are configured, simply ask Manus to QA or review a draft report. The skill will automatically execute the workflow and generate the comprehensive QA report.
