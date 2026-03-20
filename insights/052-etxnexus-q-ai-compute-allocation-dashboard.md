# etxNexus-Q: AI Compute Allocation Dashboard

## The Problem

Security firms deploying AI models for threat detection and alert triage 
have no fast way to estimate compute costs before rollout. Engineers 
prototype blind, then hit budget overruns mid-deployment.

## The Solution

etxNexus-Q is a self-contained compute cost calculator and node monitoring 
dashboard built in React + TypeScript. Security teams input model parameters, 
expected traffic, and latency targets: the calculator returns Q-Credit 
projections per second, hour, day, and month. No external APIs. No backend.

## Pages

- Home: Live node health stats (active nodes, credits/hour, avg latency)
- Allocator: Compute Cost Calculator with real-time slider-driven projections
- Network: Mocked node grid showing active vs offline infrastructure

## Use Cases

- Pre-deployment cost estimation for AI-powered SOC tools
- Proof-of-concept dashboards for MDR platform demos
- Internal tooling for teams running LLM-based threat triage at scale

## Impact

- Demonstrates that prototype-speed UI delivery is now a competitive 
  advantage for security automation shops
- Zero external dependencies: fully demoable offline

Built by Kunsh Tanwar | ETXcyberops | kunsh@etxhuman.com

<img width="800" alt="HD29bdnboAUbckE.png" src="https://dolpjhqzwsxbllsoqfnk.supabase.co/storage/v1/object/public/insight-attachments/insights/etxnexus-q-ai-compute-allocation-dashboard/HD29bdnboAUbckE.png" />
<img width="800" alt="brave_screenshot_vm-vcboex69y8i002uz03hvid.vusercontent.net.png" src="https://dolpjhqzwsxbllsoqfnk.supabase.co/storage/v1/object/public/insight-attachments/insights/etxnexus-q-ai-compute-allocation-dashboard/brave_screenshot_vm-vcboex69y8i002uz03hvid.vusercontent.net.png" />
<img width="800" alt="0c2a3e4b-9353-4e37-b88f-7050a499b3be.png" src="https://dolpjhqzwsxbllsoqfnk.supabase.co/storage/v1/object/public/insight-attachments/insights/etxnexus-q-ai-compute-allocation-dashboard/0c2a3e4b-9353-4e37-b88f-7050a499b3be.png" />
