#*******************************************************************************
# return_city_name_data_frame -- function to create a dataframe for city list 
# Usage Example:
# return_city_name_data_frame(NtnDataGeo, 2, 3)
#*******************************************************************************
return_city_name_data_frame <- function(geo_dataset, lat, lon) {
  l<- nrow(geo_dataset)
  tmp<-lapply(1:l, function(y) {
      if(!is.na(geo_dataset[y,lat]) && !is.na(geo_dataset[y,lon])){
          print(geo_dataset[y,lon])
          return(return_city_name(as.numeric(geo_dataset[y,lat]), as.numeric(geo_dataset[y,lon])))
      } 
      else{
        return(NA)
      }
  })
}
