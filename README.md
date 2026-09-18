# TMDB Movie Explorer

A responsive ASP.NET Core MVC web application that integrates with The Movie Database (TMDB) API to provide comprehensive movie discovery, search, and detailed information browsing.

![ASP.NET Core](https://img.shields.io/badge/ASP.NET%20Core-8.0-blue)
![C#](https://img.shields.io/badge/C%23-12.0-green)
![Bootstrap](https://img.shields.io/badge/Bootstrap-5.0-purple)
![TMDB API](https://img.shields.io/badge/TMDB-API-orange)

## Features

- **Browse Popular Movies** - Discover trending and popular films
- **Top Rated Movies** - Explore critically acclaimed cinema
- **Now Playing** - Check out movies currently in theaters  
- **Advanced Search** - Find movies by title, actor, or keyword
- **Responsive Design** - Optimized for desktop, tablet, and mobile
- **Secure API Management** - Protected API keys using ASP.NET Core User Secrets
- **Detailed Movie Info** - Comprehensive data including ratings, genres, cast, and production details
- **Pagination** - Efficient browsing through large movie datasets
- **Error Handling** - Graceful handling of network issues and API failures

## Technologies Used

### Backend
- **ASP.NET Core MVC 8.0** - Web framework
- **C# 12.0** - Programming language
- **HttpClient** - API communication
- **Newtonsoft.Json** - JSON serialization
- **Dependency Injection** - Service management
- **User Secrets** - Secure configuration

### Frontend
- **Razor Views** - Server-side rendering
- **Bootstrap 5** - CSS framework
- **Font Awesome** - Icon library
- **jQuery** - JavaScript functionality
- **Responsive Grid System** - Mobile-first design

### External API
- **The Movie Database (TMDB) API** - Movie data source

## Prerequisites

- [.NET 8.0 SDK](https://dotnet.microsoft.com/download/dotnet/8.0) or later
- [Visual Studio 2022](https://visualstudio.microsoft.com/) or [Visual Studio Code](https://code.visualstudio.com/)
- [TMDB API Key](https://www.themoviedb.org/settings/api) (free registration required)

## Getting Started

### 1. Clone the Repository
```bash
git clone https://github.com/aimanazuman/TMDBMovieExplorer.git
cd TMDBMovieExplorer
```

### 2. Get TMDB API Key
1. Visit [The Movie Database](https://www.themoviedb.org/)
2. Create a free account
3. Go to [API Settings](https://www.themoviedb.org/settings/api)
4. Request an API key
5. Copy your API key (you'll need it in step 4)

### 3. Restore Dependencies
```bash
dotnet restore
```

### 4. Configure API Key (User Secrets)
```bash
# Initialize user secrets
dotnet user-secrets init

# Set your TMDB API key
dotnet user-secrets set "TMDB:ApiKey" "your_api_key_here"
```

### 5. Run the Application
```bash
dotnet run
```

Or press `F5` in Visual Studio.

### 6. Open in Browser
Navigate to `https://localhost:5001` or `http://localhost:5000`

## Project Structure

```
TMDBMovieExplorer/
├── Controllers/
│   ├── HomeController.cs          # Home page and about
│   └── MoviesController.cs        # Movie browsing and details
├── Models/
│   └── MovieModels.cs             # Data models for TMDB API
├── Services/
│   └── TMDBService.cs             # API integration service
├── Views/
│   ├── Home/
│   │   ├── Index.cshtml           # Homepage with featured movies
│   │   └── About.cshtml           # Team and project info
│   ├── Movies/
│   │   ├── Index.cshtml           # Movie categories (Popular, Top Rated, etc.)
│   │   ├── Search.cshtml          # Search results
│   │   └── Details.cshtml         # Detailed movie information
│   └── Shared/
│       └── _Layout.cshtml         # Main layout with navigation
├── wwwroot/
│   ├── css/                       # Stylesheets
│   ├── js/                        # JavaScript files
│   └── images/                    # Static images
└── Program.cs                     # Application configuration
```

## Usage Examples

### Browsing Movies
- **Home Page**: View featured movies from different categories
- **Popular Movies**: `/Movies?category=popular`
- **Top Rated**: `/Movies?category=top-rated` 
- **Now Playing**: `/Movies?category=now-playing`

### Searching
- Use the search bar in the navigation
- Or visit: `/Movies/Search?query=avengers`

### Movie Details
- Click on any movie card to view detailed information
- URL format: `/Movies/Details/{movieId}`

## ⚙️ Configuration

### API Settings
The application uses User Secrets for secure API key storage:

```json
{
  "TMDB": {
    "ApiKey": "your_api_key_here"
  }
}
```

### Production Configuration
For production deployment, set the API key using environment variables:
```bash
export TMDB__ApiKey="your_production_api_key"
```

## Security Features

- **User Secrets** - API keys stored securely outside project directory
- **Input Validation** - Search queries and parameters are validated
- **Error Sanitization** - No sensitive information exposed in error messages
- **HTTPS Enforcement** - Secure communication enforced
- **Request Rate Limiting** - Respects TMDB API rate limits

## Screenshots

### Home Page
- Hero section with featured movies
- Categories: Popular, Top Rated, Now Playing
- Responsive movie cards with ratings

### Movie Browsing
- Grid layout with movie posters
- Filtering by categories
- Pagination for large datasets
- Hover effects and smooth transitions

### Search Functionality
- Global search bar in navigation
- Search results with pagination
- Empty state handling
- Error messages for failed searches

### Movie Details
- Hero section with backdrop image
- Comprehensive movie information
- Rating visualization with progress bars
- Production company logos and genres

## Error Handling

The application includes comprehensive error handling:

- **Network Errors** - Graceful handling of connection issues
- **API Rate Limits** - Proper HTTP status code handling
- **Invalid Responses** - JSON parsing error management
- **Missing Data** - Default images and fallback content
- **User-Friendly Messages** - Technical errors converted to readable text

## Learning Outcomes

This project demonstrates:

- **Third-party API Integration** - RESTful API consumption
- **Secure Configuration Management** - User Secrets and environment variables
- **Async Programming** - Non-blocking HTTP operations
- **Error Handling Strategies** - Multi-layer error management
- **Responsive Web Design** - Mobile-first approach
- **MVC Architecture** - Separation of concerns
- **Dependency Injection** - Proper service registration
- **Modern C# Patterns** - Latest language features

## 🎓 Academic Context

**Course**: Web API Development 
**Course Code**: SWC3633/SWC4443 - Web API Development
**Objective**: CLO2 - Build consumer Web APIs using third-party API
**Assignment Type**: Pair Programming (2 students maximum)

### Assignment Requirements Fulfilled
- [X] Third-party API integration (TMDB)
- [X] Secure API key management
- [X] Multiple page user flow
- [X] Error handling implementation
- [X] Home and About Us pages
- [X] Professional code structure
- [X] GitHub repository with documentation

## Team

- **Student 1**: Fakeh Ikwan Hakim - AM2408016617
  - Role: Frontend Development & UI/UX Design
  - Responsibilities: View implementation, responsive design, user experience

- **Student 2**: Muhammad Aiman Iskandar - AM2408016618  
  - Role: Backend Development & API Integration
  - Responsibilities: Service layer, API integration, error handling

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## License

It's a free to use project :)

## Acknowledgments

- **The Movie Database (TMDB)** - For providing the comprehensive movie API
- **Bootstrap Team** - For the excellent CSS framework
- **Font Awesome** - For the beautiful icon library
- **Microsoft** - For ASP.NET Core and excellent documentation
- **Course Instructors** - For guidance and assignment requirements

## Support

If you encounter any issues:

1. Check the [Issues](https://github.com/aimanazuman/TMDBMovieExplorer/issues) section
2. Verify your TMDB API key is correctly configured
3. Ensure all dependencies are restored (`dotnet restore`)
4. Check the application logs for detailed error information

---

**If you found this project helpful, please give it a star!**

---

*This project was developed as part of the Web API Development course (SWC3633/SWC4443) to demonstrate third-party API integration using ASP.NET Core MVC.*
