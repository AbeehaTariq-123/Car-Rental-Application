# 🚗 Car Rental Application

A clean, responsive car rental web application built with **ASP.NET Core MVC** and **Bootstrap 5.3**. Users can browse available cars, book one with a single click, and review all booked cars in a tidy table.

The project demonstrates core MVC concepts: models, controllers, strongly typed Razor views, shared layouts, and POST-Redirect-GET navigation. All data is kept in memory, so it needs no database or extra setup.

---

## ✨ Features

- **Browse available cars** in a responsive card grid with name, daily price in PKR, and an "Available" badge
- **One-click booking**: a POST form moves the selected car from the available list to the booked list
- **Booked cars table** with striped rows, hover effect, and a "Booked" status badge
- **Responsive layout**: dark navbar that collapses behind a toggle button on small screens
- **Friendly empty states**: Bootstrap info alerts when no cars are available or none are booked
- **Shared layout** with a navigation bar, centred container, and footer

---

## 🛠️ Tech Stack

| Area | Technology |
|------|------------|
| Framework | ASP.NET Core MVC (.NET 8) |
| Language | C# |
| Views | Razor (strongly typed) |
| Styling | Bootstrap 5.3 (CDN) |
| Data | In-memory static lists |
| IDE | Visual Studio |

---

## 📁 Project Structure

```
Car Rental Application/
├── Controllers/
│   └── CarsController.cs      # Index, Book, Booked actions
├── Models/
│   └── Car.cs                 # Id, Name, PricePerDay
├── Views/
│   ├── Cars/
│   │   ├── Index.cshtml       # Available cars (card grid)
│   │   └── Booked.cshtml      # Booked cars (table)
│   └── Shared/
│       └── _Layout.cshtml     # Navbar, container, footer
└── Program.cs                 # Default route points to Cars/Index
```

---

## ⚙️ How It Works

The app uses a single `Car` model and two static lists inside `CarsController`:

- `availableCars`: starts with three sample cars
- `bookedCars`: starts empty

| Action | Method | Description |
|--------|--------|-------------|
| `Index` | GET | Sends `availableCars` to the Index view |
| `Book` | POST | Finds the car by ID, moves it from `availableCars` to `bookedCars`, then redirects to `Booked`. If the car is not available, it returns to `Index` without changes |
| `Booked` | GET | Sends `bookedCars` to the Booked view |

### Sample data

| ID | Car | Price per day |
|----|-----|---------------|
| 1 | Alto | PKR 3,000 |
| 2 | Corolla | PKR 6,000 |
| 3 | Civic | PKR 8,000 |

---

## 🚀 Getting Started

### Prerequisites

- [.NET 8 SDK](https://dotnet.microsoft.com/download/dotnet/8.0)
- [Visual Studio](https://visualstudio.microsoft.com/) with the **ASP.NET and web development** workload (optional, you can also use the command line)

### Run locally

```bash
git clone https://github.com/AbeehaTariq-123/<repo-name>.git
cd <repo-name>
dotnet run
```

Or open `Car Rental Application.csproj` in Visual Studio and press **F5**.

The app opens on the Available Cars page.

---

## 🧪 Try It Out

1. Click **Book Car** on any car, and you are taken to the Booked Cars page
2. Click **Back to Cars**, and the booked car no longer appears
3. Book every car to see the "no cars available" message
4. Resize the browser to see the navbar collapse

---
