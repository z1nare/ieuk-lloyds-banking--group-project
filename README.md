# [Internship Experience UK](https://www.brightnetwork.co.uk/internship-experience-uk/): [Lloyds Banking Group](https://www.lloydsbankinggroup.com/) Engineering project
## July 2025. Sector Skills Project: Engineering.

## Project Overview:
### I've joined a small but fast-growing music media startup facing critical server performance issues due to a surge in web traffic. While the increase in visitors is a positive sign of growth, some traffic appears to be non-human (bots), overwhelming the servers and causing frequent downtime. This project uses log file analysis to diagnose traffic patterns, identify potential bot traffic, and suggest cost-effective mitigation strategies that can be implemented by a small engineering team.

## Objective:
* Analyze web server logs to identify suspicious or excessive activity.

* Determine the root cause of frequent service disruptions.

* Recommend affordable and scalable solutions for bot management and traffic control.
  
## 🗂 Project Structure

- `ieuk-project.ipynb` – Jupyter notebook with full analysis
- `REPORT.md` – Summary of findings and recommendations
- `plots/` – Folder with generated graphs
  
## Getting Started

Follow these instructions to set up the project and run the analysis on your local machine.

### Prerequisites
* Python 3.8 or higher
* pip (Python package installer)

### Installation & Usage

1.  **Clone the repository:**
    ```sh
    git clone https://github.com/z1nare/ieuk-lloyds-project.git
    cd your-repo-name
    ```

2.  **Create and activate a virtual environment (recommended):**
    ```sh
    # For macOS/Linux
    python3 -m venv venv
    source venv/bin/activate

    # For Windows
    python -m venv venv
    .\venv\Scripts\activate
    ```

3.  **Install the required libraries:**
    ```sh
    pip install -r requirements.txt
    ```

4.  **Launch Jupyter Notebook:**
    ```sh
    jupyter notebook
    ```
    Once Jupyter launches in your browser, open the `ieuk-project.ipynb` file to view the code and analysis. The final report can be found in `REPORT.md`.
