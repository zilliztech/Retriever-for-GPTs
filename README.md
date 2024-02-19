# GPTs-ZillizPipline
**[GPTs](https://openai.com/blog/introducing-gpts)** are custom versions of ChatGPT that combine instructions, extra knowledge, and any combination of skills.

**[Zilliz Cloud Pipelines](https://zilliz.com/zilliz-cloud-pipelines)** provides a solution that enables easy and efficient transformations of unstructured data into high-quality vector embeddings, significantly lowering the barrier to developing AI-powered capabilities like RAG.

# Quick Start
**This tutorial shows how to use Zilliz Pipeline to build your own GPTs with RAG ability.**

In this quick start guide, we built a GPTs **Ask about 2023** that can inform users about events that occurred in 2023.
- try the demo here: https://chat.openai.com/g/g-CXDhOVcGf-ask-about-2023

## Step 1. Ingest docs via Zilliz Cloud Pipelines
1. Sign up for Zilliz Cloud: Visit https://zilliz.com/ and create an account.
2. Create Pipelines: Initiate an ingestion pipeline and a search pipeline on Zilliz Cloud. Note down the **search pipeline ID**: pipe-******** and your **API-Key**.

   <img src="images/pipeline.png" width="80%"  alt=""/>

3. Ingest Documents: Navigate to the Pipeline Playground, enter the _doc_url_ field, and click Run to ingest documents.

   - for example, for **Ask about 2023**, we can ingest a PDF file that contains the events of 2023.
    ```markdown
    "doc_url": "https://raw.githubusercontent.com/wxywb/raw_resources/master/2023.pdf"
    ```
    <img src="images/run_pipeline.png" width="100%"  alt=""/>

- check [zilliz pipeline rag](https://github.com/milvus-io/bootcamp/blob/master/bootcamp/RAG/zilliz_pipeline_rag.ipynb) for detailed instructions about how to create zilliz pipeline.
## Step 2. Create GPTs
1. Visit https://chat.openai.com/gpts/editor to create a new GPTs.
2. Fill in the GPT name and its description. For example, Ask about 2023.
3. Optionally, upload a photo for the GPT.

<img src="images/create_gpts.png" width="80%"  alt=""/>

## Step 3. Add GPT Action
1. Select **Add GPT Action** to introduce a new action.

   <img src="images/create_actions.png" width="30%"  alt=""/>

2. Insert the content from the YAML file [rag.yaml](openapi%2Frag.yaml) into the GPT action Schema field.
3. Substitute SearchPipelineID with your previously noted search pipeline ID: pipe-**********.
   <img src="images/action_schema.png" width="80%"  alt=""/>
4. For authentication:
  - Click Authentication.
  - Choose API-key as the Authentication Type and Bearer as the Auth Type.
  - Enter the API-Key provided by Zilliz Cloud.

   <img src="images/auth.png" width="50%"  alt=""/>

5. Add the Privacy Policy URL: https://openai.com/policies/terms-of-use

## Step 4. Configure GPTs Instructions
GPTs require instructions to guide their behavior. The instructions should be clear and concise, providing a comprehensive understanding of the GPT's capabilities and limitations.

The instructions should include 2 parts, the first part is the general instructions for the GPTs, and the second part is the prompt for the RAG ability.
1. In the Configure tab, input instructions for the GPTs.
   - For example, for **Ask about 2023**, the instructions are as follows:
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

2. After the instructions above, input the instructions from [rag_prompt.json](prompt%2Frag_prompt.json) to enable RAG ability for the GPTs.
  
<img src="images/instructions.png" width="80%"  alt=""/>

3. Introduce conversation starters to guide users on interacting with your GPT.

<img src="images/start.png" width="80%"  alt=""/>

## Step 5. Publish Your GPTs
1. Click Save to make your GPT accessible to users.

   <img src="images/publish.png" width="30%"  alt=""/>

## Step 6. Chat with Your GPTs
1. Access the GPTs page, select the GPT you've created, and start asking questions.

   <img src="images/demo.png" width="100%"  alt=""/>

### Support

If you require any assistance or have questions regarding the GPTs-Zilliz Pipeline integration, please feel free to reach out to our support team: Email: support@zilliz.com

# Appendix
- [Introducing Zilliz Cloud Pipelines: A One-Stop Service for Building AI-Powered Search](https://zilliz.com/blog/introducing-zilliz-cloud-pipelines-one-stop-service-building-ai-powered-search)
- [Introducing GPTs](https://openai.com/blog/introducing-gpts)
- [rag.yaml](openapi%2Frag.yaml)
- [rag.md](prompt%2Frag.md)
- [2023.pdf](https://raw.githubusercontent.com/wxywb/raw_resources/master/2023.pdf)
- [Zilliz Cloud](https://www.zilliz.com)
- [OpenAI](https://openai.com)