# Cloud Sync Setup

VowSuite works offline with browser local storage by default. For shared access across devices, the Studio tab includes an optional Supabase cloud sync panel.

## What You Need

- A Supabase project URL.
- The Supabase `anon` public key.
- One shared sync ID for the couple. Use the app's generated ID so it includes a random suffix.

Never paste a Supabase service role key into the app. The anon key is the only key intended for browser use.

## Supabase Table

Create this table in the Supabase SQL editor:

```sql
create table if not exists public.wedding_plans (
  id text primary key,
  data jsonb not null,
  updated_at timestamptz not null default now()
);

alter table public.wedding_plans enable row level security;

create policy "basic shared wedding plan read"
on public.wedding_plans
for select
using (true);

create policy "basic shared wedding plan write"
on public.wedding_plans
for insert
with check (true);

create policy "basic shared wedding plan update"
on public.wedding_plans
for update
using (true)
with check (true);
```

This policy is designed for a simple shared workspace. Anyone with the project URL, anon key, and sync ID can read or update that plan, so do not use it as-is for private production client data. A generated sync ID is harder to guess, but it is not a replacement for authentication.

## In The App

1. Open the live app.
2. Go to `Studio management`.
3. Paste the Supabase project URL and anon public key.
4. Generate or enter the same shared sync ID on every device.
5. On the first device, choose `Push`.
6. On another device, choose `Pull`.

`Auto-push local changes` can be enabled after the first successful push/pull. Manual push/pull is safer while setting up a new couple.

## Production Upgrade Path

For real client use, add authentication, planner/couple roles, restricted row policies, file storage rules, and an audit log. The static app is ready to call a hosted data layer, but privacy depends on the Supabase policies you configure.
