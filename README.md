# Pypostgres

![Python](https://img.shields.io/badge/Python-3.12-blue.svg)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-Compatible-brightgreen.svg)
![License](https://img.shields.io/badge/License-MIT-yellow.svg)

A powerful Python interface for PostgreSQL databases that simplifies database interactions and query management.

## Features

- Simplified PostgreSQL connection management
- Easy query execution and result handling
- Support for parameterized queries to prevent SQL injection
- Transaction management utilities
- Connection pooling for improved performance
- Comprehensive error handling and logging

## Installation

```bash
# Clone the repository
git clone https://github.com/Ayman-aa/pypostgres.git
cd pypostegres

# Create and activate a virtual environment (optional but recommended)
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Optionnaly 
pip install -r requirements_for_env.txt
```

## Usage

```python
# Import the main class
from my_py_postegres import DatabaseManager

# Create a database manager instance
db_manager = DatabaseManager()

# Connect to your database
db_manager.selected_db = "your_database"
db_manager.setup()

# Execute a raw query with parameters
success, results = db_manager.execute_raw_query(
    "SELECT * FROM users WHERE active = %s", 
    [True]
)

# Process results
if success:
    for row in results:
        print(f"User: {row['username']}, Email: {row['email']}")

# Close the connection when done
db_manager.close()
```

Or alternatively use the CLI:

```bash
python3 pypostegres.main
```

## Dependencies

- Python 3.12+
- psycopg2-binary 2.9.10+

## Documentation

Coming not soon

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## Imagery

<details>
<summary>Click to view screenshots</summary>

### Database Connection Screen
![Database Connection Screen](assets/open.JPG)

### Listing Tables
![Listing Tables](assets/listing_tables.JPG)

### Standard Query
![Standard Query](assets/query.JPG)

</details>

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- [psycopg2](https://www.psycopg.org/) - PostgreSQL adapter for Python
- All contributors who have helped this project grow