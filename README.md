# Examining Coral Spawning of the Florida Keys Reef
*Capstone project for the YSE ENvironmental Data Science Certificate.*
*Shayne Doone November 2026

## Project Description
Coral reef cover in the Florida Reef Tract has been declining for decades and it poses severe environmental and economic problems to the surrounding areas. Coral reefs are a foundational species that support a range of life in addition to the economic prosperity they bring for coastal communities. Tracking and understanding spawning yield are changing is vital in the efforts to restore this species. In addition to understanding the yield it is important to record and learn what genotypes are still reproducing to ensure genetic variability remains. 

## Research Question
** How has coral spawning changed in the Florida Reef Tract from 2020 to 2025 and how do the conditions and genotypes influence performance?

## Data
| File |         Description        | Source |
|------|----------------------------|--------|
|raw_data/CREMP_SCOR_Summaries_LTA_2024_.csv | Coral Reef Evaluation and Monitoring Programs recording from 2011-2024 for Stony Coral species cover| [ Florida Fish and Wildlife's /  CREMP_SCOR_Summaries_LTA_2024, https://geodata.myfwc.com/documents/2ab2e706c83d4247855f8e4e689c7cba/about] - downloaded 11/15/26
#Still anticipating data from MOTE Marine Laboratory for further monitoring data.

## Repository Structure
├──README.md    <- This serves as the information directory and you are currently here
├── raw_data/  <- This is the original unedited data
    ├── CREMP_SCOR_Summaries_LTA_2024_.csv
├──clean_data/  <- output of 1_data_clean.ipynb
    ├── fl_coral_cover_2024_f.csv
├── figures/    <- plots and tables
├── scripts/    <- notebooks, ordered chronologically
    ├──0_project_setup.ipynb
    ├──1_data_clean.ipynb

## How to run the code
All scripts are written in R using Google Colab notebooks. These scripts run in chronological order
1. scripts/0_project_setup.ipynb creates the project folder and subfolders in Google Drive.
2. scripts/1_data_clean.ipynb reads the raw data files, filters them, cleans them and writes fl_coral_cover_2024_f.csv
Each notebook mounts Google Drive with the initial cell utilizing Python ('drive.mount()'), then switches to the R runtime. See the notes at the top of each notebook.

## Data Cleaning Steps ('1_data_clean.ipynb')
1. Following the step where the raw data is read in and names to ('fl_coral_presence_raw') this data is then filtered to only include the sample year of 2024. This decreases the rows from 2197 to 160. The function dim('fl_coral_presence_2024') was used to determine the new row count.
2. The naming used in the raw data could cause confusion later, so all of the column names, other than the species names, were changed to be formatted to name_name instead of using capitol letters.
3. The second column, sample date was originally categorized as a character string instead of date so this was changed utilizing the mutate function and the as.date function.
    
  **Known Data Issues**
   At this point in time some of the data that is still in the data set may not be necessary for the capstone project. I plan to remove the data the further along in the project we get.

   ## Status and Next Steps
   - [x] set up the project folder and GitHub Repo
   - [x] clean and combine raw data
   - [ ] import more of the data set from Mote, this current data will be used to show what the current coral cover looks like, while the spawning data will help draw more conclusions about coral reproduction
   - [ ] Exploratory plots: reproduction abundance by location, temperature, and genetic makeup
   - [ ] colocate reproduction locations from Mote with FFWC monitoring infromation
   - [ ] create ecological model that can predict future reproduction

