# SendEmailAutomation

A Python automation that downloads an Excel sales file from Google Drive, calculates total revenue and units sold, and emails the results through Gmail.

**Knowledge areas:** Robotic Process Automation (RPA) · GUI automation · Spreadsheet data processing · Sales reporting

**Tech stack:** Python · Jupyter Notebook · PyAutoGUI · pandas · openpyxl · Pyperclip · Excel (.xlsx) · Google Drive · Gmail · macOS

## How it works

1. **Download the sales data.** PyAutoGUI opens Safari through Spotlight and uses mouse clicks and keyboard shortcuts to download the spreadsheet from Google Drive.
2. **Calculate the sales metrics.** pandas reads the Excel file using openpyxl. The notebook sums the `Valor Final` column for total revenue and the `Quantidade` column for units sold.
3. **Send the report.** PyAutoGUI opens Gmail in Chrome. Pyperclip puts the subject and the generated report on the clipboard so the automation can paste them into Gmail and send the message with a keyboard shortcut.

## Run locally

1. On macOS, install Safari and Chrome if needed. Install the Python dependencies:

   ```bash
   python3 -m pip install notebook pyautogui pandas openpyxl pyperclip
   ```

2. Open [main.ipynb](main.ipynb) in Jupyter Notebook. Set the Google Drive folder URL, the local spreadsheet path, and the recipient address. The spreadsheet must include the `Valor Final` and `Quantidade` columns.
3. Make sure your browser sessions can access the Drive folder and Gmail. Enable Gmail keyboard shortcuts and grant macOS Accessibility permission to the app running the notebook if prompted.
4. Adjust the click coordinates for your screen. The last cell uses `pyautogui.position()` to help you find them.
5. Run the workflow cells in order. Use a test recipient on the first run because the send cell sends a real email.

The workflow starts manually and uses the browser interface. Changes to the layout, screen resolution, or page load times may require adjusting the click coordinates or delays.
