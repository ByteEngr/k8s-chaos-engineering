# Contributing to K8s Chaos Engineering

Thank you for your interest in contributing to **K8s Chaos Engineering**!  
This project is part of the **DigitalOcean Open Source Program** to promote chaos engineering and system resilience in cloud-native environments.

---

## 📜 Code of Conduct

Please read and follow our [Code of Conduct](CODE_OF_CONDUCT.md) before contributing.

---

## 🛠️ How to Contribute

### 🐞 Reporting Issues

1. Check if the issue already exists in the [Issues](https://github.com/akintunero/k8s-chaos-engineering/issues) section.
2. If not, open a new issue including:
   - ✅ Clear and descriptive title  
   - 📝 Detailed problem description  
   - 🔁 Steps to reproduce  
   - 📊 Expected vs actual behavior  
   - 🧩 Environment details (Kubernetes version, OS, etc.)

---

### 🔀 Pull Requests

1. Fork the repository.
2. Create a new branch for your feature or bugfix.
3. Make your changes.
4. Add or update tests as needed.
5. Update documentation if applicable.
6. Open a pull request with:
   - ✨ Clear summary of your changes
   - 🔗 Link to relevant issues
   - 📷 Screenshots or demo videos (if needed)

---

## 🧪 Development Setup

```bash
# Clone the repository
git clone https://github.com/ByteEngr/k8s-chaos-engineering.git
cd k8s-chaos-engineering

# Install dependencies
brew install kubectl minikube helm

# Start your local cluster
minikube start

# Set up LitmusChaos
helm repo add litmuschaos https://litmuschaos.github.io/litmus-helm/
helm repo update


### Code Style

- Follow the existing code style
- Use meaningful variable and function names
- Add comments for complex logic
- Keep functions small and focused
- Write tests for new functionality

### Documentation

- Update README.md for significant changes
- Add inline documentation for complex code
- Update API documentation if needed
- Keep the documentation up-to-date

### Testing

- Write unit tests for new features
- Run existing tests before submitting PR
- Ensure all tests pass
- Add integration tests for complex features

### Review Process

1. Pull requests will be reviewed by maintainers
2. Address any feedback or requested changes
3. Once approved, your changes will be merged

## Getting Help

- Join our [Slack channel](https://slack.litmuschaos.io/)
- Check our [documentation](https://docs.litmuschaos.io/)
- Open an issue for questions or problems

##  Maintainers

This project is maintained by:

**Goziechukwu Chima-Duru**  
GitHub: [@ByteEngr](https://github.com/ByteEngr)  
📧 Email: [chimadurugoodness@gmail.com](mailto:chimadurugoodness@gmail.com)

## License

By contributing, you agree that your contributions will be licensed under the [Apache License 2.0](LICENSE).

Thank you for contributing to K8s Chaos Engineering! 
