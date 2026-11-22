# 🤝 Contribution Guidelines

Thank you for contributing to the **Online Auction System**!

## Code Conventions
- Follow standard Java naming conventions (CamelCase for classes, lowerCamelCase for methods/variables).
- Maintain strict **Encapsulation**: fields must be `private`; provide getters only where state exposure is necessary.
- Keep business validation inside domain models (e.g., bidding rules in `Auction.java`).

## Workflow for Pull Requests
1. Create a feature or documentation branch from `main`.
2. Ensure the code compiles cleanly using:
   ```bash
   javac *.java
   ```
3. Test all menu options and negative test cases.
4. Submit a Pull Request describing the proposed enhancement.
