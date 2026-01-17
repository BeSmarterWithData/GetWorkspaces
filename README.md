# Simple Workspace Export Script

A lightweight PowerShell script to quickly export Power BI workspace information to Excel.

## What It Does

This script provides a simple, streamlined way to:
1. Connect to Power BI Service (Public Cloud)
2. Automatically detect your access level (Admin or User)
3. Retrieve workspaces (up to 5000)
4. Export workspace details to Excel

## Features

- ✅ **Automatic Module Installation** - Installs ImportExcel and MicrosoftPowerBIMgmt if needed
- ✅ **Smart Access Detection** - Automatically detects if you have admin API access
- ✅ **Dual Mode Operation**:
  - **Admin Mode**: Retrieves up to 5000 workspaces using admin APIs
  - **User Mode**: Retrieves workspaces you have access to
- ✅ **Excel Export** - Formatted Excel file with filters, frozen header row, and auto-sized columns
- ✅ **No Pre-requisites** - Modules install at user level, no admin rights required

## Quick Start

### Option 1: Run the .ps1 File

1. Download `Simple Workspace Export Script.ps1`
2. Right-click and select "Run with PowerShell"
3. Sign in when prompted
4. Excel file opens automatically when complete

### Option 2: Copy and Paste

1. Open `Simple Workspace Export Script.txt`
2. Copy the entire contents
3. Open PowerShell
4. Paste and press Enter
5. Sign in when prompted
6. Excel file opens automatically when complete

## Output

The script creates an Excel file named:
```
PowerBI_Workspaces_Export_YYYYMMDD_HHMMSS.xlsx
```

### Exported Fields

- **Workspace ID** - Unique identifier
- **Workspace Name** - Display name
- **Type** - Workspace type (e.g., Workspace, PersonalGroup)
- **State** - Current state (Active, Deleted, etc.)
- **Is Read Only** - Read-only flag
- **Is On Dedicated Capacity** - Premium/capacity indicator
- **Capacity ID** - Associated capacity ID
- **Description** - Workspace description

## Requirements

- PowerShell 5.1 or higher
- Internet connection
- Power BI account (Public Cloud)

## Permissions

### User Mode
- Access to Power BI Service
- Standard user permissions
- Returns only workspaces you have access to

### Admin Mode (Optional)
- Power BI/Fabric Tenant Administrator role
- Returns up to 5000 workspaces across the entire tenant
- Script automatically detects and uses admin APIs if available

## Troubleshooting

### Module Installation Issues
- **Issue**: "Cannot install module"
- **Solution**: The script installs modules at user level. No admin rights needed.

### Authentication Fails
- **Issue**: "Failed to authenticate"
- **Solution**: 
  - Ensure you have internet access
  - Verify you're using a valid Power BI account
  - Check that you're connecting to Public Cloud

### No Workspaces Found
- **Issue**: "No workspaces found"
- **Solution**: 
  - Verify you have access to at least one workspace
  - Check that you're signed in with the correct account

### Excel File Won't Open
- **Issue**: File created but won't open
- **Solution**: 
  - Ensure Excel is installed
  - Check file path: Should be in same folder as script
  - Manually open the file from the specified path

## Differences from Main Scripts

This simplified script is designed for quick workspace exports and differs from the main governance scripts:

| Feature | Simple Script | Main Scripts |
|---------|--------------|--------------|
| Workspace Export | ✅ | ✅ |
| Report Backups | ❌ | ✅ |
| Model Backups | ❌ | ✅ |
| Dataflow Backups | ❌ | ✅ |
| Impact Analysis | ❌ | ✅ |
| Metadata Extraction | ❌ | ✅ |
| Temporary Access Management | ❌ | ✅ |
| Service Principal Auth | ❌ | ✅ (separate script) |
| Sovereign Cloud Support | ❌ | ✅ |

**Use this script when you:**
- Need a quick workspace inventory
- Don't need full governance/backup features
- Want minimal setup and execution time

**Use the main scripts when you:**
- Need comprehensive governance and impact analysis
- Want to backup reports, models, and dataflows
- Require full metadata extraction

## Sovereign Cloud Support

Currently, this script is designed for **Public Cloud only**. 

For sovereign cloud support (Germany, USGov, China, USGovHigh, USGovMil), use the main governance scripts:
- `Final PS Script.txt` - For interactive authentication
- `Final PS Script - Service Principal.txt` - For service principal authentication

## Related Files

- **Main Governance Solution**: `Final PS Script.txt`
- **Service Principal Version**: `Final PS Script - Service Principal.txt`
- **Main Documentation**: [README.md](README.md)
- **Service Principal Guide**: [README - Service Principal.md](README%20-%20Service%20Principal.md)

## Support

For issues or questions:
- Open an issue on the GitHub repository
- Include the error message
- Specify if you're using Admin or User mode

## License

This script is part of the Power BI Admin Governance & Impact Analysis Solution.
See [LICENSE](LICENSE) for details.
