# Explore AI Agent Development

In this exercise, you use the **Azure AI Agent** service in the **Azure AI Foundry** portal to create a simple AI agent that assists employees with expense claims.

> ⏱️ **Estimated Time:** 30 minutes  
> ⚠️ **Note:** Some of the technologies used in this exercise are in preview or active development. You may experience unexpected behavior, warnings, or errors.

---

## 🚀 Step 1: Create an Azure AI Foundry Project and Agent

Let's start by creating an Azure AI Foundry project.

1. Open a web browser and navigate to: [https://ai.azure.com](https://ai.azure.com)
2. Sign in with the credentials below:
   - **Username:** ``
   - **Password:** ``
3. Close any tips or quick start panes that appear.
4. If necessary, click the **Azure AI Foundry** logo at the top-left to return to the home page.

> 🖼️ You should now see the Azure AI Foundry home page.

5. Select **Create an agent**.
6. When prompted to create a project, enter the name:
7. Expand **Advanced options** and set the following:

- **Azure AI Foundry resource:** *(enter a valid resource name)*
- **Subscription:** *Your Azure subscription*
- **Resource group:** `ResourceGroup1`
- **Region:** *Select any AI Foundry recommended region*

> ⚠️ Some Azure AI resources are constrained by regional model quotas. If a quota limit is exceeded, you may need to switch regions.

8. Click **Create** and wait for the project to be created.
9. If prompted, deploy a **gpt-4o model** using either **Global standard** or **Standard** deployment type.
10. Set the **Tokens per minute (TPM)** limit to `50000`, or the maximum available.

> ⚠️ Reducing TPM helps avoid exceeding quota limits. 50K is sufficient for this lab.

11. Once the project is created, the **Agents playground** opens automatically.

> 🧠 A GPT-4o base model is automatically deployed when the agent is created.

---

## 🤖 Step 2: Create Your Agent

Next, you'll create an agent that can answer questions based on a corporate expenses policy.

1. Open a new browser tab and download the expenses policy document:  
[Expenses_Policy.docx](https://raw.githubusercontent.com/MicrosoftLearning/mslearn-ai-agents/main/Labfiles/01-agent-fundamentals/Expenses_Policy.docx)

2. Return to the **Foundry Agents playground**.

3. In the **Setup** pane:
- Set the **Agent name** to: `ExpensesAgent`
- Ensure the **gpt-4o** deployment is selected.
- Set the **Instructions** as below:
    You are an AI assistant for corporate expenses.
    You answer questions about expenses based on the expenses policy data.
    If a user wants to submit an expense claim, you get their email address, a description of the claim, and the amount to be claimed and write the claim details to a text file that the user can download.
  
4. Scroll to the **Knowledge** section and click **+ Add**:
- Select **Files**
- In the dialog, create a new vector store named: `Expenses_Vector_Store`
- Upload the `Expenses_Policy.docx` file downloaded earlier

5. Verify that `Expenses_Vector_Store` is listed and contains **1 file**.

6. In the **Actions** section, click **+ Add**:
- Select **Code interpreter**
- Click **Save** (no file upload required)

> ✅ Your agent now has a knowledge base and code interpreter support.

---

## 🧪 Step 3: Test Your Agent

You can now test the agent in the playground chat.

1. In the chat window, enter the prompt: "What's the maximum I can claim for meals?
- The agent should respond using the expenses policy document.

> ⚠️ If the agent fails to respond due to a rate limit, wait a few seconds and try again.

2. Enter a follow-up prompt: "I'd like to submit a claim for a meal."
- The agent should request your email address.

3. Provide an email address, for example: "fred@contoso.com"
4. Submit the claim details, for example:  "Breakfast cost me $20."

- The agent should generate a downloadable text file with the expense claim details.

5. Download and open the generated file to review the submitted claim.

---

> 📝 **You’ve successfully created and tested an AI Agent using Azure AI Foundry!**


