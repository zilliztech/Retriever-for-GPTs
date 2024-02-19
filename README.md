# GPTs-ZillizPipline
**GPTs** are custom versions of ChatGPT that combine instructions, extra knowledge, and any combination of skills.
- https://openai.com/blog/introducing-gpts

**Zilliz Pipeline** provides a solution that enables easy and efficient transformations of unstructured data into high-quality vector embeddings, significantly lowering the barrier to developing AI-powered capabilities like RAG.
- https://zilliz.com/blog/introducing-zilliz-cloud-pipelines-one-stop-service-building-ai-powered-search

# Quick Start
This tutorial shows how to use Zilliz Pipeline to build your own GPTs with RAG ability.

In this quick start guide, we built a GPTs that can inform users about events that occurred in 2023.
- try the demo here: https://chat.openai.com/g/g-CXDhOVcGf-zilliz-pipeline-demo

## Step 1. Ingest docs into ZillizCloud via Zilliz Pipeline
1. Create Pipelines: Initiate an ingestion pipeline and a search pipeline on Zilliz Cloud. Note down the search pipeline ID: pipe-60991ddff7ccd8ac8c0207.

-<img src="images/pipeline.png" width="80%"  alt=""/>

2. Ingest Documents: Navigate to the Pipeline Playground, enter the doc_url field, and click Run to ingest documents into Zilliz Cloud.
```markdown
"doc_url": "https://raw.githubusercontent.com/wxywb/raw_resources/master/2023.pdf"
```
<img src="images/run_pipeline.png" width="100%"  alt=""/>

- check https://docs.zilliz.com/docs/create-pipelines for detailed instructions about how to create zilliz pipeline.
## Step 2. Create GPTs
1. Visit https://chat.openai.com/gpts/editor to create a new GPTs.
2. Fill in the GPT name and its description.
3. Optionally, upload a photo for the GPT.

<img src="images/create_gpts.png" width="80%"  alt=""/>

## Step 3. Add GPT Action
1. Select **Add GPT Action** to introduce a new action.

<img src="images/create_actions.png" width="30%"  alt=""/>

2. Insert the content from the YAML file [rag.yaml](openapi%2Frag.yaml) into the GPT action Schema field.

<img src="images/action_schema.png" width="80%"  alt=""/>

3. Substitute SearchPipelineID with your previously noted search pipeline ID: pipe-60991ddff7ccd8ac8c0207..
4. For authentication:
  - Click Authentication.
  - Choose API-key as the Authentication Type and Bearer as the Auth Type.
  - Enter the API-Key provided by Zilliz Cloud.

<img src="images/auth.png" width="50%"  alt=""/>

5. Add the Privacy Policy URL: https://openai.com/policies/terms-of-use

## Step 4. Configure GPT Prompts
1. In the Configure tab, input instructions for the GPTs.
```markdown
This GPT is designed to inform users about events that occurred in 2023. It provides summaries, insights, and detailed
accounts of significant happenings from that year. It aims to be informative, engaging, and accurate in its
descriptions, ensuring users receive a comprehensive understanding of the year's events. When asked, it will focus on
delivering concise information about specific incidents, trends, developments in various fields such as technology,
global politics, health, and culture. It will avoid speculation and stick to verified information to maintain
credibility.

In cases where details are not clear or are disputed, the GPT may clarify that the information is based on available
sources as of its last training cut-off in April 2023. It will encourage users to consult up-to-date sources for the
latest information. The GPT is friendly and approachable in its tone, making historical information accessible and
interesting to a wide audience. It avoids sensitive topics with respect and care, ensuring that discussions are handled
with empathy and awareness of their complexity.

```
2. After the instructions above, input the prompt from [rag.md](prompt%2Frag.md) to enable RAG ability for the GPTs.
3. Introduce conversation starters to guide users on interacting with your GPT.

<img src="images/instructions.png" width="80%"  alt=""/>

## Step 5. Publish Your GPTs
1. Click Save to make your GPT accessible to users.

<img src="images/publish.png" width="30%"  alt=""/>

## Step 6. Engage with Your GPTs
1. Access the GPTs page, select the GPT you've created, and start asking questions.

<img src="images/demo.png" width="100%"  alt=""/>

### Support

If you require any assistance or have questions regarding the Kafka Connect Milvus Connector, please feel free to reach out to our support team: Email: support@zilliz.com

# Appendix
- [Introducing Zilliz Cloud Pipelines: A One-Stop Service for Building AI-Powered Search](https://zilliz.com/blog/introducing-zilliz-cloud-pipelines-one-stop-service-building-ai-powered-search)
- [Introducing GPTs](https://openai.com/blog/introducing-gpts)
- [rag.yaml](openapi%2Frag.yaml)
- [rag.md](prompt%2Frag.md)
- [2023.pdf](https://raw.githubusercontent.com/wxywb/raw_resources/master/2023.pdf)
- [Zilliz Cloud](https://www.zilliz.com)
- [OpenAI](https://openai.com)