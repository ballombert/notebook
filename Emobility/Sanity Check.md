
Goal :  give the CCC a sanity status of the platform

- [ ] Create a simple in e2e sanity scenario :
	- Create a simulate Charger
	- Enrol it 
	- Activated it
	- Check the charger status
- [ ] Create a pipeline on a schedule Once every X min
- [ ] Add to CCC an API to add a sanity check log 
```json
"Sanity Log": {
	"Date": "2023-01-19 13:35:31"
	"Category" : "e2e-sanity",
	"Test":"Enrolement of a charger",
	"Result": "Ok", // OK, Faild
	"Info": "Creation"
}
``` 
- [ ] Add a step in sanity scenario to put the result of the test
- [ ] Add an CCC an API to get all the last logs for a category and test 
- [ ] Add a UI display in the dashboard to see the sanity check log (ex: Green light)
