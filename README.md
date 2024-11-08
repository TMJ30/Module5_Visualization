# Module5_Visualization

**Pymaceuticals, Inc. Homwork Summary:**

"You've just joined Pymaceuticals, Inc., a new pharmaceutical company that specializes in anti-cancer medications. Recently, it began screening for potential treatments for squamous cell carcinoma (SCC), a commonly occurring form of skin cancer.

As a senior data analyst at the company, you've been given access to the complete data from their most recent animal study. In this study, 249 mice who were identified with SCC tumors received treatment with a range of drug regimens. Over the course of 45 days, tumor development was observed and measured. The purpose of this study was to compare the performance of Pymaceuticals’ drug of interest, Capomulin, against the other treatment regimens.

The executive team has tasked you with generating all of the tables and figures needed for the technical report of the clinical study. They have also asked you for a top-level summary of the study results."


**Code Sources:**

Used to produce summary statistics in a single line (Sourced from student xpert learning assistant)
   
    tumor_stats = mouse_study_clean.groupby("Drug Regimen")["Tumor Volume (mm3)"].agg(
        
        mean='mean',
       
        median='median',
        
        variance='var',
        
        std_dev='std',
        sem=lambda x: x.std() / (len(x) ** 0.5)  # Standard Error of the Mean
    
    ).rename_axis('Drug Regimen').reset_index().set_index('Drug Regimen')

Used to clean DataFrame by dropping the duplicate mouse by its ID (Sourced from professor Ali)

      mouse_study_clean = mouse_studydf[mouse_studydf["Mouse ID"].isin(mice_duplictaes)==False]   

  
