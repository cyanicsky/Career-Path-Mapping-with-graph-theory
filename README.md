# Career-Path-Mapping-with-graph-theory
### Overview
This project uses graph theory to model and analyze career paths for various applicants, assessing their fit for managerial roles based on roles, skills, and experiences.

### Requirements
- Python 3.x
- Required Libraries:
  - `networkx`
  - `matplotlib`
  - `math`

Install the libraries using:
```bash
pip install networkx matplotlib
```

### Files and Scripts
1. **Career Path Data:**
   - Data for applicants is stored in the `career_paths` dictionary, containing roles, skills, and other attributes.

2. **Manager Role Requirements:**
   - Defined in the `manager_requirements` dictionary, specifying the skills, roles, and behavioral attributes needed.

3. **Functions:**
   - **`analyze_fit_for_manager()`**: Analyzes an applicant's fit for the manager role.
   - **`identify_missing_requirements()`**: Identifies missing roles, skills, and gaps for each applicant, and finds the shortest path to the manager role.

4. **Visualization:**
   - Generates a directed graph to represent career paths.
   - Highlights paths for specific applicants and displays fit scores.

5. **Radar Charts:**
   - Plots radar charts to visualize fit scores for all applicants across role, skill, and behavioral fit.

### How to Use
1. **Analyze Fit for Manager Role:**
   ```python
   fit_scores = {}
   for applicant, data in career_paths.items():
       fit_score = analyze_fit_for_manager(data, manager_requirements)
       fit_scores[applicant] = fit_score
   print(fit_scores)
   ```

2. **Visualize Career Paths:**
   Create a graph visualization of career paths:
   ```python
   nx.draw(G, pos, with_labels=True, node_size=3000, node_color='lightblue')
   ```

3. **Identify Missing Requirements:**
   Check gaps in roles and skills for each applicant:
   ```python
   missing_roles, missing_skills, behavioral_gaps = identify_missing_requirements(applicant_data, G, manager_requirements)
   ```

### Error Handling
- Ensure that all roles in the applicant's career path are correctly represented in the graph.
- Verify that input data for each applicant matches the expected structure.

---

## Repository Structure
```
HR-Analytics-and-Career-Path-Mapping/
│
├── Project1_Preprocessing_and_HR_Report_Automation/
│   ├── preprocessing_scripts.py
│   ├── data_analysis.py
│   ├── visualization_scripts.py
│   ├── generate_pdf_report.py
│   └── NewImages/ (Generated images)
│
└── Project2_Career_Path_Mapping_with_Graph_Theory/
    ├── career_path_data.py
    ├── graph_visualization.py
    ├── analyze_fit.py
    └── career_path_graph.png (Generated graph)
```

### Contribution
Feel free to fork the repository, raise issues, or submit pull requests for any enhancements or bug fixes. 

### Contact
For any inquiries, please contact the repository maintainers.

--- 

This README should provide a comprehensive guide to understanding and using the projects within the repository.

### README for Career Path Analysis with Graph Theory

This project leverages graph theory and the `networkx` library to model and analyze career paths for different applicants. It includes visualizations and analytical functions to assess the fit of various applicants for managerial roles based on their skills, roles, and experiences. Below is a guide to using the scripts and understanding their functionality.

#### Requirements

1. **Python Libraries:**
   - `networkx`
   - `matplotlib`
   - `math`

2. **Installation:**
   You can install the required libraries using the following commands:
   ```bash
   pip install networkx matplotlib
   ```

#### File Overview

1. **Career Path Data:**
   The `career_paths` dictionary contains sample data for five applicants, detailing their roles, skills, behavioral skills, mentoring experience, coaching received, network influence, and career aspirations.

2. **Manager Requirements:**
   The `manager_requirements` dictionary outlines the necessary roles, skills, behavioral attributes, mentoring and coaching experience, and network influence required for the manager position.

3. **Function Definitions:**
   - **`analyze_fit_for_manager(applicant_data, requirements)`:** Analyzes the fit of an applicant for the manager role based on their career path and skills.
   - **`create_radar_chart_for_all(applicants_data, requirements)`:** Generates a radar chart visualizing role fit, skill fit, and behavioral fit for all applicants.
   - **`identify_missing_requirements(applicant, career_graph, requirements)`:** Identifies gaps in roles, skills, and behavioral attributes, and finds the shortest path to the manager role using graph theory.

4. **Visualization:**
   - **Career Path Graph:** A directed graph is created to represent the career progression of each applicant. Nodes represent roles, and edges represent the transitions between roles with skill requirements as attributes.
   - **Radar Chart:** Displays the fit of each applicant for the manager role based on their role, skill, and behavioral fit.

5. **Example Usage:**
   The file contains example code for calculating and displaying the fit score for each applicant against the manager requirements. It also visualizes the career paths and highlights the path for a selected applicant (e.g., `Applicant_3`).

#### How to Use

1. **Fit Analysis:**
   Run the script to see the fit scores of each applicant for the manager role. This will print the percentage fit for each applicant.

   ```python
   fit_scores = {}
   for applicant, data in career_paths.items():
       fit_score = analyze_fit_for_manager(data, manager_requirements)
       fit_scores[applicant] = fit_score
   ```

2. **Visualization:**
   To visualize the career paths of applicants, run the provided graph visualization code. This will display a network graph of career progressions with highlighted paths for specific applicants.

   ```python
   pos = nx.spring_layout(G)
   nx.draw(G, pos, with_labels=True, node_size=3000, node_color='lightblue', font_size=10, font_weight='bold', arrowsize=20)
   ```

3. **Radar Chart:**
   Create a radar chart to visualize the fit scores for all applicants:

   ```python
   create_radar_chart_for_all(career_paths, manager_requirements)
   ```

4. **Identifying Gaps:**
   Use the `identify_missing_requirements` function to find missing roles, skills, and other gaps for any applicant. The function also provides the shortest path to the manager role:

   ```python
   missing_roles, missing_skills, behavioral_gaps, mentoring_gap, coaching_gap, network_gap, path_to_manager = identify_missing_requirements(applicant_data, G, manager_requirements)
   ```

#### Error Handling

1. **ValueError in Graph Visualization:**
   If you encounter a `ValueError` while visualizing paths for an applicant, ensure that all roles in the applicant's career path are correctly mapped in the graph.

2. **Inconsistent Data:**
   Ensure that the roles and skills in the applicant data are consistent with those defined in the `manager_requirements`.

#### Conclusion

This project provides a structured approach to analyzing career paths using graph theory, enabling effective career planning and role fit analysis. By modifying the sample data and requirements, you can customize this tool to suit different roles and skill sets.

For further assistance or queries, please refer to the comments within the code or reach out to me :)))