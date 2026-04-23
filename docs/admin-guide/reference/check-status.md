---
description: >-
sidebar_label: "Check Status"
sidebar_position: 4
---

# Check Status

The status of the different containers can be viewed using the command:

```bash
sudo docker compose ps
```

The system health check status will be indicated in the STATUS column:

* **exited (X):** The container process has stopped, where X is the exit code (0 usually means it finished its job; any other number usually means a crash).
* **restarting:** The container crashed or stopped, and Docker is trying to bring it back up based on the restart policy.
* **paused:** The container is still "running" in memory, but all processes have been suspended (usually via `docker pause`).
* **created:** The container has been initialized but has not been started yet.
* **healthy:** The service is up and running and basic checks pass.
* **unhealthy:** The container is running, but the health check command failed multiple times in a row.
* **unhealthy (starting):** The initial checks failed, but it hasn't reached the "retries" limit to be fully declared unhealthy.

