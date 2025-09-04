## Overview
When something happens, Kisi's platform create events. They are of two types: access events and audit events. 
Access events are related to physical actions like a door being unlocked, someone forcing a door open, or someone tries to open a door with their card and their access is denied. 
Audit events are everything relating to admnistration like creating a new user is added or a new schedule for when the door should be opened.
These events can trigger automatic follow-up actions, either inside Kisi or in external systems through APIs and webhooks, enabling automation and integrations.
For that purpose, the events are forwarded in real time as JSON payloads via configurable **HTTP webhooks**, with support for **event filtering**.


## Example Use Cases
- **Slack alert on access denied at sensitive location:** When `access_denied` fires, send a message to the security channel with user, door, and timestamp for quick follow-up.
- **Security Ticketing:** What can constitute a security risk is escalated to launch a security alert. If a door is forced open, the corresponding forced_open event triggers a webhook to your Incident Management system (e.g., PagerDuty) to raise and escalate a security alert.
- **Usage analytics at gym:** Log every “door_unlocked” event to analyze peak hours, helping the gym optimize staffing and class schedules.  


## Sample Event (JSON payload when a customer named Alice opens the gym entrance door)
```json
{
  "uuid": "a3f02c9b-91b4-42b3-9cd2-8f9d6a512345",
  "actor_type": "User",
  "actor_id": 4521,
  "actor_name": "Alice Smith",
  "object_type": "Lock",
  "object_id": 102,
  "object_name": "Gym Entrance",
  "organization_id": 56,
  "place_id": 12,
  "success": true,
  "type": "lock.unlock",
  "error_code": null,
  "error_message": null,
  "created_at": "2025-09-04T09:32:15Z"
}

