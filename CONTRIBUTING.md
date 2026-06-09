# Contributing Guidelines

Thank you for your interest in contributing to this project.

## How to Contribute

1. Fork the repository.
2. Create a feature branch:

```bash
git checkout -b feature/your-feature-name
```

3. Install dependencies:

```bash
pip install -r requirements.txt
```

4. Run tests before committing:

```bash
pytest
```

5. Commit your changes with a clear message:

```bash
git commit -m "Add meaningful feature description"
```

6. Push your branch and open a pull request.

## Code Style

- Keep functions small and focused.
- Use descriptive variable names.
- Add tests for new logic.
- Avoid committing secrets, credentials, datasets with personal information, or generated model artifacts unless explicitly required.

## Pull Request Checklist

- [ ] Code runs locally
- [ ] Tests pass
- [ ] Documentation updated
- [ ] No secrets committed
- [ ] Changes are focused and easy to review

## Medical Safety Note

This project is not a medical device. Contributions should avoid making unsupported clinical claims.
