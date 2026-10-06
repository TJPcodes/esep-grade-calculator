# ESEP Grade Calculator

A small Go library for figuring out a student's final grade. There are three kinds of grades: assignments, exams, and essays. Each kind gets averaged, the averages are weighted, and the total is turned into a letter grade.

## Requirements
- Go 1.24 or newer (run `go version` to check, or download it at https://go.dev/dl)
- Git

## Setup
```
git clone https://github.com/TJPcodes/esep-grade-calculator.git
cd esep-grade-calculator/grade-calculator
```
Heads up: the folder is `grade-calculator` with a hyphen, not `grade_calculator`.

## Project structure
| File | What it does |
|------|---------|
| `grade-calculator/go.mod` | Module definition (module name and Go version) |
| `grade-calculator/grade_calculator.go` | The library itself: `GradeCalculator`, `AddGrade`, `GetFinalGrade` |
| `grade-calculator/grade_calculator_test.go` | Unit tests |

## Usage
```go
gc := NewGradeCalculator()
gc.AddGrade("homework 1", 95, Assignment)
gc.AddGrade("midterm", 88, Exam)
gc.AddGrade("essay 1", 90, Essay)
letter := gc.GetFinalGrade() // "A", "B", "C", "D", or "F"
```

## Running the tests
Run these from inside the `grade-calculator` folder.

Run the tests:
```
go test ./...
```

Same thing, with more detail:
```
go test -v ./...
```

See the coverage percentage:
```
go test -cover ./...
```

Make a coverage report and open it in your browser:
```
go test -coverprofile=coverage.out ./...
go tool cover -html=coverage.out
```