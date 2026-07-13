=== STEP 1: PROJECT SETUP ===
Project setup complete!
CSV file    : data/titanic.csv
JSON output : data/titanic_processed.json

=== STEP 2: DATA LOADED ===
Dataset loaded successfully! Shape: (891, 12)
Columns: ['PassengerId', 'Survived', 'Pclass', 'Name', 'Sex', 'Age', 'SibSp',
          'Parch', 'Ticket', 'Fare', 'Cabin', 'Embarked']

=== STEP 3: DESCRIPTIVE STATISTICS ===
Mean / median / std calculated for all numeric columns
(Age mean ≈ 29.70, Fare mean ≈ 32.20 — both match expected values)

=== STEP 4: MISSING VALUES ===
Columns with missing data (most → least): ['Cabin', 'Age', 'Embarked']

=== STEP 5: FEATURE ENGINEERING ===
Created: FamilySize, IsAlone, AgeGroup, Title

Survival rate by IsAlone (0 = with family, 1 = alone):
IsAlone
0    0.506
1    0.304

Survival rate by AgeGroup:
Adult          0.418
Child          0.540
Senior         0.365
Unknown        0.294
Young Adult    0.351

Survival rate by Title:
Mrs       0.794
Miss      0.703
Master    0.575
Rare      0.348
Mr        0.157

=== STEP 6: CLASS-BASED JSON EXPORT ===
Built 891 Passenger objects.

Summary statistics:
  total_passengers: 891
  survived: 342
  did_not_survive: 549
  survival_rate: 0.3838
  average_age: 29.7
  average_fare: 32.2
Data exported to data/titanic_processed.json

=== STEP 7: VALIDATION ===
  [PASS] Top-level keys present
  [PASS] Passenger count matches DataFrame
  [PASS] Every passenger has 12 fields
  [PASS] Summary total == passenger count
  [PASS] Survived + did_not_survive == total

Sample passenger record:
{
  "passenger_id": 1,
  "name": "Braund, Mr. Owen Harris",
  "age": 22.0,
  "sex": "male",
  "survived": 0,
  "pclass": 3,
  "fare": 7.25,
  "embarked": "S",
  "family_size": 2,
  "is_alone": 0,
  "age_group": "Young Adult",
  "title": "Mr"
}

Validation PASSED