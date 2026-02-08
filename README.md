# Automated Medical Transcript Processing with ICD-10 Code Extraction

## Project Overview

This project leverages the OpenAI API to automatically extract structured medical information from unstructured clinical transcripts and map treatments to standardized ICD-10 billing codes. The solution addresses a critical challenge in healthcare: converting dense medical narratives into structured data for insurance claims, billing, and medical documentation.

## Problem Statement

Medical professionals document patient encounters in natural language transcripts that contain important details about symptoms, diagnoses, and treatments. However, extracting key information from these transcripts manually is:

- Time-consuming and labor-intensive
- Prone to human error
- Difficult to scale across large healthcare networks
- Essential for accurate billing and insurance claims processing

## Solution

This automated system uses OpenAI's GPT-4o-mini model with function calling to:

1. Extract patient age and recommended treatments from medical transcripts
2. Retrieve corresponding ICD-10 codes for each treatment
3. Generate structured datasets ready for billing and analysis
4. Provide quality metrics and cost estimates for the extraction process

## Features

- Automated extraction of patient demographics and treatment information
- ICD-10 code mapping using AI-powered medical knowledge
- Data quality analysis and validation
- Statistical summaries and visualizations
- Cost estimation for API usage
- Support for multiple medical specialties
- Export functionality for downstream systems

## Technologies Used

- **Python 3.8+**
- **OpenAI API** (GPT-4o-mini model)
- **Pandas** for data manipulation
- **Matplotlib** for data visualization
- **JSON** for structured data handling

## Dataset

The project uses anonymized medical transcriptions categorized by specialty:

- **Source**: Medical transcription dataset
- **Format**: CSV file with specialty and transcription columns
- **Specialties**: Multiple medical specialties including Allergy/Immunology, Orthopedic, Bariatrics, Cardiovascular, Urology, and more


### Setup Instructions

1. Clone the repository:
```bash
git clone https://github.com/yourusername/medical-transcript-processing.git
cd medical-transcript-processing
```

2. Install required packages:
```bash
pip install -r requirements.txt
```

3. Set up your OpenAI API key:
```bash
export OPENAI_API_KEY='your-api-key-here'
```

Or create a `.env` file:
```
OPENAI_API_KEY=your-api-key-here
```

4. Place your data file in the `data/` directory:
```
data/transcriptions.csv
```

## using OpenAI
   - Retrieve ICD-10 codes
   - Analyze results and generate visualizations
   - Export processed data

### Key Functions

**extract_info_with_openai(transcription)**
- Extracts patient age and recommended treatment from a transcript
- Returns structured JSON with age and treatment fields
- Handles missing information gracefully

**get_icd_codes(treatment)**
- Retrieves ICD-10 codes for a given treatment or procedure
- Uses OpenAI API for accurate medical code mapping
- Returns code list or 'Unknown' if not applicable


## Results

The system successfully:

- Processes medical transcripts across multiple specialties
- Achieves high extraction accuracy for patient age and treatments
- Maps treatments to appropriate ICD-10 codes
- Provides quality metrics and success rates
- Generates cost-effective automated documentation

### Sample Output

| Age | Recommended Treatment/Procedure | Medical Specialty | ICD Code |
|-----|--------------------------------|-------------------|----------|
| 23  | Zyrtec and Nasonex nasal spray | Allergy/Immunology | J30.9, R06.7 |
| 41  | Surgical repair of Achilles tendon | Orthopedic | S86.011A, 0LQN0ZZ |

## Analysis Features

- Patient age distribution statistics and visualization
- Treatment patterns across medical specialties
- Most frequent ICD-10 codes analysis
- Data quality and extraction success metrics
- API cost estimation and optimization

## Cost Considerations

The project uses GPT-4o-mini for cost-effective processing:

- Input tokens: ~$0.150 per 1M tokens
- Output tokens: ~$0.600 per 1M tokens
- Average cost per transcript: Less than $0.01

## Limitations

- Accuracy depends on the quality and completeness of source transcripts
- ICD-10 code mapping may require medical professional validation
- API costs scale linearly with dataset size
- Processing time depends on API rate limits

## Future Enhancements

- Add support for additional medical codes (CPT, SNOMED)
- Implement batch processing for larger datasets
- Add confidence scores for extracted information
- Integrate with electronic health record (EHR) systems
- Develop a web interface for real-time processing
- Add multi-language support for international use


