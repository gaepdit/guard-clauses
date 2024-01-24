# Georgia EPD-IT Guard Clauses Library

This package was created by Georgia EPD-IT to provide simple guard clause methods for our web applications.

[![Georgia EPD-IT](https://raw.githubusercontent.com/gaepdit/gaepd-brand/main/blinkies/blinkies.cafe-gaepdit.gif)](https://github.com/gaepdit)
[![.NET Test](https://github.com/gaepdit/guard-clauses/actions/workflows/dotnet.yml/badge.svg)](https://github.com/gaepdit/guard-clauses/actions/workflows/dotnet.yml)
[![CodeQL](https://github.com/gaepdit/guard-clauses/actions/workflows/codeql-analysis.yml/badge.svg)](https://github.com/gaepdit/guard-clauses/actions/workflows/codeql-analysis.yml)
[![SonarCloud Quality Gate Status](https://sonarcloud.io/api/project_badges/measure?project=gaepdit_guard-clauses&metric=alert_status)](https://sonarcloud.io/summary/new_code?id=gaepdit_guard-clauses)
[![Lines of Code](https://sonarcloud.io/api/project_badges/measure?project=gaepdit_guard-clauses&metric=ncloc)](https://sonarcloud.io/summary/new_code?id=gaepdit_guard-clauses)

This package was inspired by the great [GuardClauses](https://github.com/ardalis/GuardClauses/tree/main) package by
Steve Smith, which has a lot more options and extensibility.

## How to install

[![Nuget](https://img.shields.io/nuget/v/GaEpd.GuardClauses)](https://www.nuget.org/packages/GaEpd.GuardClauses)

To install, search for "GaEpd.GuardClauses" in the NuGet package manager or run the following command:

`dotnet add package GaEpd.GuardClauses`

## How to use

Guard clauses simplify checking for invalid input parameters.

Example usage:

```csharp
public class SomeClass
{
    private readonly string _name;

    public SomeClass(string name)
    {
        _name = Guard.NotNullOrWhiteSpace(name);
    }
}
```

Each clause returns the original value if the conditions are met; otherwise, it throws an exception.

- `NotNull` – ensures a value is not null.
- `NotNullOrWhiteSpace` – ensures a string is not null, empty, or whitespace.
- `ValidLength` – ensures a string has a length between the specified minimum and maximum (inclusive).
- `NotNegative` – ensures an integer is not negative.
- `Positive` – ensures an integer is not zero or negative.
- `RegexMatch` – ensures a string matches the provided regex pattern.
