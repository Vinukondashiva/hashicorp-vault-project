# hashicorp-vault-project
A project demonstrating secure secrets management using HashiCorp Vault and Docker.
# Secure Secrets Management with HashiCorp Vault and Docker

## Project Summary
This project demonstrates the setup and configuration of a local secrets management server using HashiCorp Vault, containerized with Docker. The primary goal was to gain hands-on experience with the core workflow of a Privileged Access Management (PAM) tool by securely storing, managing, and retrieving application secrets, thereby avoiding the insecure practice of hardcoding sensitive data in code.

For a detailed walkthrough with screenshots, please see the [**Full Project Report PDF**](./HashiCorp_Vault_Project_Report_1.pdf) in this repository.

## Technologies Used
* **HashiCorp Vault:** A tool for securely storing and accessing secrets.
* **Docker:** A containerization platform used to run the Vault instance locally.
* **PowerShell (Windows Terminal):** Used to execute Docker commands.

## Key Features Implemented
* **Dockerized Vault Instance:** Deployed a Vault server in a secure, isolated development environment using a single Docker command.
* **Server Initialization:** Learned the concept of the **Unseal Key** and **Root Token**, which are fundamental to Vault's security architecture.
* **Authentication:** Successfully authenticated to the Vault UI using a Root Token.
* **Secrets Management:** Created a new secret at a specific path (`my-app/database`) to store key-value data representing application credentials.
* **Secure Retrieval:** Viewed the stored secret through the UI, demonstrating the complete create/read workflow.

## How to Run This Setup
1.  **Ensure Docker is installed** and running on your machine.
2.  **Run the Vault container** using the following command in your terminal:
    ```bash
    docker run --cap-add=IPC_LOCK -p 8200:8200 --name dev-vault hashicorp/vault
    ```
3.  **Get the Root Token** by checking the container's logs:
    ```bash
    docker logs dev-vault
    ```
4.  **Access the UI** by navigating to `http://localhost:8200/` and use the Root Token to sign in.

## Project Conclusion
This project provided a practical, hands-on introduction to secrets management. It successfully demonstrated the core workflow of running a Vault instance, authenticating, and performing basic create/read operations. This experience highlighted the critical importance of decoupling secrets from application code and how tools like Vault provide a secure, centralized solution for this task.
