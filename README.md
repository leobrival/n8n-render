# Install n8n on Render.com with Supabase

Quick guide to set up n8n on Render.com using Supabase as the PostgreSQL database.

## Prerequisites

- Accounts on [Render.com](https://render.com) & [Supabase](https://supabase.com)

## Steps

### 1. Create a Supabase Database

1. Sign up at [supabase.com](https://supabase.com).
2. Create a new project, name it, set a password.
3. Go to **Settings > Database**; note:
   - **Host**
   - **Port**: `5432`
   - **Database**: your DB name
   - **User**: `postgres`
   - **Password**: the one you set

### 2. Deploy n8n on Render

1. Deploy n8n on Render using the button below:
   > _(Insert "Deploy to Render" button here)_
2. On **Create a New Web Service**:
   - Name your service.
   - Select **Docker** as the environment.
3. Add your environment variables.

> **Note:** Replace `${}` values with actual Supabase details.

Click **Create Web Service**.

### 3. Set `WEBHOOK_URL`

- After deployment, copy your Render service URL (e.g., `https://n8n.onrender.com`).
- Update `WEBHOOK_URL` in **Environment** with this URL and redeploy.

### 4. Prevent Sleep

To prevent your n8n instance from going idle, import the keep-alive workflow from `default_workflow.json`.

Render puts unused instances to sleep, which can cause delays in response and interrupt workflows. A "keep-alive" workflow ensures regular activity, keeping your instance responsive and active.

#### Import Workflow

1. Access your n8n instance.
2. Navigate to **Workflow > Import from File**.
3. Upload the `default_workflow.json` file containing:

Activate the workflow to keep the instance active.

> **Note:** Make sure to replace `https://WEBHOOK_URL/healthz` with your actual `WEBHOOK_URL`.

### 5. Test

Test your n8n instance by creating a simple workflow.

### Resources

- [n8n Docs](https://docs.n8n.io/)
- [Supabase Docs](https://supabase.com/docs)
- [Render Docs](https://render.com/docs)

---

Created by Léo Brival for Topographic Studio.
