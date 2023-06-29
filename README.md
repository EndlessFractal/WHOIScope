# WHOIS Domain Lookup Tool

WHOIScope simplifies the WHOIS information extraction by leveraging multiple WHOIS servers and providing the option to save the results to files.

## Usage

1. Clone the repository:

   ```shell
   git clone https://github.com/NotoriusNeo/WHOIScope
   ```

2. Navigate to the project directory:

   ```shell
   cd WHOIScope
   ```

3. Install the required dependencies:

   ```shell
   pip install -r requirements.txt
   ```

4. Run the script:

   ```shell
   python3 WHOIScope.py
   ```

   Note: Other Python versions may work, but the script was built with Python 3.11 in mind.

5. Follow the prompts to enter the domain you want to check.

6. The script will query the appropriate WHOIS server and retrieve information about the domain. The results will be displayed in the terminal and saved to a text file.

   **Example Output:**

   ```plaintext
   +-------------------+----------------------------------------+
   |     Attribute     |                 Value                  |
   +-------------------+----------------------------------------+
   | domain_name       | example.com                            |
   | registrar         | Registrar Name                         |
   | registration_date | 2023-01-01 12:00:00                    |
   | expiration_date   | 2024-01-01 12:00:00                    |
   | name_servers      | ['ns1.example.com', 'ns2.example.com'] |
   +-------------------+----------------------------------------+
   ```

   The table will be saved to a text file with a filename in the format `YYYY-MM-DD_HH-MM-SS_whois_example.com.txt`.

## How It Works

1. The script uses the `os` module to change the working directory to the directory where the script is located. This ensures that the generated text file is saved in the same directory.

2. The `query_whois` function takes a domain name as input and selects the appropriate WHOIS server based on the domain's TLD. It then queries the WHOIS server using the `whois` library and returns the WHOIS information as a dictionary.

3. The main code block prompts the user to enter a domain to check and calls the `query_whois` function to retrieve the WHOIS information for the domain.

4. The retrieved WHOIS information is displayed in a formatted table using the `PrettyTable` class from the `prettytable` library. If a value is a list of datetime objects, each element is added to the table on a separate line.

5. The script generates a filename for the text file using the current timestamp and saves the table to the file.

6. The filename of the saved text file is displayed to the user.

## Note

**Disclaimer:**
Please use WHOIScope responsibly and in compliance with ethical hacking guidelines. The script is provided as-is without any warranty. The developer is not responsible for any misuse or damage caused by the script.
