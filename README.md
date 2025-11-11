# Testcontainer Skills
A comprehensive skills library for writing robust async tests with Python testcontainers in Claude Code.

## What You Get
- **Testcontainer Setup** - Best practices for Docker test containers
- **Async Testing Patterns** - Proper async/await patterns with pytest
- **Configuration Management** - pytest conftest.py patterns and fixtures
- **Container Lifecycle** - Setup, teardown, and cleanup workflows
- **Testing Workflows** - Systematic approaches to integration testing

Plus:
- **Automatic Integration** - Skills activate automatically when working with testcontainers
- **Consistent Workflows** - Proven patterns for container-based testing
- **Python Async Support** - Modern async/await patterns with asyncio

## Learn More
Read the skill documentation in `skills/testcontainer-python-async/SKILL.md`

## Installation

### Claude Code (via Plugin Marketplace)

First, register the Kwik-E-Mart marketplace:

```bash
/plugin marketplace add appunni-m/claude-marketplace
```

Then install the plugin from this marketplace:

```bash
/plugin install testcontainer@kwik-e-mart
```

### Direct Installation (via URL)

You can also install directly from the GitHub repository:

```bash
/plugin add https://github.com/appunni-m/cl-testcontainer.git
```

## Verify Installation

Check that the skill is available:

```bash
/skills
# Should see:
# testcontainer-python-async - Skills for writing tests using Python testcontainers with async support
```

## Quick Start

### Using the Skill

The skill activates automatically when you're:
- Setting up testcontainer-based tests
- Writing async pytest fixtures
- Configuring Docker containers for testing
- Debugging container lifecycle issues

You can also manually invoke it:

```bash
/skill testcontainer-python-async
```

## What's Inside

### Skills Library

**Testcontainer Python Async** (`skills/testcontainer-python-async/`)
- Container setup and configuration patterns
- Async fixture management with pytest
- Root conftest.py best practices
- Container lifecycle management
- Integration testing workflows
- Error handling and debugging

### Examples

Check `skills/testcontainer-python-async/examples/` for:
- Sample conftest.py configurations
- Common testing patterns
- Real-world usage examples

## How It Works

- **Skills System** - Uses Claude Code's first-party skills system
- **Automatic Discovery** - Claude finds and uses the skill when working with testcontainers
- **Best Practices** - Encodes proven patterns for container-based testing

## Philosophy

- **Test Isolation** - Each test gets clean container state
- **Async First** - Modern async/await patterns throughout
- **Resource Management** - Proper container lifecycle and cleanup
- **Reproducibility** - Tests work consistently across environments
- **Developer Experience** - Fast feedback loops with minimal boilerplate

## Common Use Cases

### Setting Up Testcontainers
```python
# The skill helps you create proper async fixtures
@pytest_asyncio.fixture(scope="session")
async def database_container():
    container = PostgresContainer("postgres:15")
    container.start()
    yield container
    container.stop()
```

### Writing Async Tests
```python
# Proper async test patterns
@pytest.mark.asyncio
async def test_database_query(database_container):
    async with database_container.get_connection() as conn:
        result = await conn.fetch("SELECT 1")
        assert result[0][0] == 1
```

## Contributing

Skills live directly in this repository. To contribute:

1. Fork the repository
2. Create a branch for your improvement
3. Update the skill documentation in `skills/testcontainer-python-async/SKILL.md`
4. Add examples if applicable
5. Submit a PR

## Updating

Skills update automatically when you update the plugin:

```bash
/plugin update testcontainer
```

## Repository Structure

```
.
├── plugin.json                                    # Plugin metadata
├── README.md                                      # This file
├── LICENSE                                        # MIT License
└── skills/
    └── testcontainer-python-async/
        ├── SKILL.md                              # Main skill documentation
        ├── CHANGELOG.md                          # Version history
        └── examples/
            └── root_conftest.py                  # Example configurations
```

## License

MIT License - see LICENSE file for details

## Support

- **Issues**: https://github.com/appunni-m/cl-testcontainer/issues
- **Marketplace**: https://github.com/appunni-m/claude-marketplace

---

**Kwik-E-Mart**: Claude Code skills and tools available 24/7. Thank you, come again!
