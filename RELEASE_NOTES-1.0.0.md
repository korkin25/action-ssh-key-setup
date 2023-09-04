## 🚀 Release Notes

---

### 🎉 New GitHub Action

In this release, we've introduced a new GitHub action to streamline the process of SSH key setup for secure shell operations. Here are the details:

#### **SSH key Setup**

- **Description**: This action handles the setup of SSH keys, including private keys and known hosts, in your GitHub Actions environment. It also validates the SSH key type to ensure it's one of the allowed types.
  
- **Inputs**:
  - `ssh-private-key`: The private SSH key for authentication (Required).
  - `ssh-private-key-type`: The type of the private SSH key, e.g., rsa, dsa, or ecdsa. Defaults to rsa (Optional).
  - `ssh-known-hosts`: SSH known hosts for establishing the SSH connection (Required).

- **Main Features**:
  - Validates the type of the SSH private key.
  - Automatically sets up the SSH keys in the GitHub Actions environment.
  - Configures known hosts for SSH operations.

---

### 🔧 Instructions

To utilize this action in your workflow:

1. Add a new step in your workflow YAML file and use the action `korkin25/ssh-setup@main`.
2. Specify the required input parameters. Optionally, you can also specify the type of SSH key if it is other than RSA.

Example:

```yaml
- name: Setup SSH
  uses: korkin25/ssh-setup@main
  with:
    ssh-private-key: ${{ secrets.SSH_PRIVATE_KEY }}
    ssh-known-hosts: ${{ secrets.SSH_KNOWN_HOSTS }}
