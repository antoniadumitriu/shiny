# Install if not already installed
# install.packages("shiny")
# install.packages("leaflet")

# Load the packages
library(shiny)
library(leaflet)

# Define the UI
ui <- fluidPage(
  titlePanel("Edinburgh Map"),
  mainPanel(
    leafletOutput("map")
  )
)

# Define the server
server <- function(input, output) {
  output$map <- renderLeaflet({
    # Create a leaflet map centered around Edinburgh
    m <- leaflet() %>%
      setView(lng = -3.188267, lat = 55.953251, zoom = 12) %>%
      addTiles()  # Add a base layer 
    
    # Added a marker for a specific location (e.g., Edinburgh Castle)
    m <- m %>%
      addMarkers(
        data = data.frame(
          name = "Edinburgh Castle",
          lng = -3.1965,
          lat = 55.9486
        ),
        label = ~name,  # Label for the marker
        popup = ~name   # Popup text for the marker
      )
    
    m  # Return the map
  })
}

# Run the app
shinyApp(ui, server)
