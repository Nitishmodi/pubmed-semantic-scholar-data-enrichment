# pubmed-semantic-scholar-data-enrichment
Automate data enrichment with articles and abstracts sourced from PubMed and Semantic Scholar, facilitating seamless integration into research projects.
# PubMed and Semantic Scholar Data Enrichment Tool

1.This tool automates the process of enriching research data by fetching articles and abstracts from PubMed and Semantic Scholar APIs based on a list of queries provided in a CSV file.

## Changes Made from Original Code

1. **Error Handling**: Added try-except blocks to handle potential errors in PubMed and Semantic Scholar searches. Errors are caught and printed with informative messages, allowing the script to continue execution gracefully.
   ```python
   try:
       # Code block where potential errors might occur
   except Exception as e:
       print(f"Error in PubMed search: {e}")
       return []

   
2. Improved Abstract Retrieval:
   Modified to handle cases where abstracts are not available in PubMed. This ensures that the script handles missing abstracts gracefully and continues processing without crashing.
   
abstract = article.get('Abstract', {}).get('AbstractText', '')


4. Improved Query Reading:
 Wrapped query reading from the CSV file in a try-except block to handle file reading errors. This ensures that if there are any issues with reading the queries from the file, the script provides feedback and exits gracefully.

try:
    # Code block to read queries from CSV
except Exception as e:
    print(f"Error reading queries: {e}")
    return
    
4. Added Feedback:
Added print statements to provide feedback on the success or failure of CSV generation. Users are notified whether the CSV file was generated successfully or if there were any errors during the process.

try:
    # Code block to save DataFrame to CSV
    print("CSV file generated successfully.")
except Exception as e:
    print(f"Error saving to CSV: {e}")
    
Minor Fixes: Fixed indentation issues and corrected parameter types in PubMed search to ensure consistency and readability.
