# White Furred Mice Dataset

## Face	detection	and	Grimace	Scale	Prediction	of	White	Furred	Mice

Studying	the	facial	expressions	of	humans	has	been	one	of	the	major	
applications	of	computer	vision.	An	open	question	is	whether	common	machine	
learning	techniques	can	also	be	used	to	track	behaviors	of	animals,	which	is	a	
less	explored	research	problem.	Since	animals	are	not	capable	of	verbal	
communication,	computer	vision	solutions	can	provide	valuable	information	to	
track	the	animal’s	state.	We	are	particularly	interested	in	pain	neurobiology	
research,	where	rodent	models	are	extensively	used	to	investigate	pain	
interventions.	A	grimace	scale	is	used	to	understand	the	suffering	of	a	mouse	in	
the	presence	of	interventions,	which	is	inferred	from	various	facial	features	such	
as	the	shape	of	the	eyes	and	ears.	In	this	work,	we	automate	the	prediction	of	the	
grimace	scale	on	white	furred	mice	using	a	machine	learning	approach,	
following	the	same	principles	used	for	human	facial	expression	recognition:	face	
detection,	landmark	region	extraction,	and	expression	recognition.	We	
demonstrate	the	use	of	the	you	only look	once	(YOLO)	framework	for	face	
detection	of	the	mice	with	outstanding	results.	For	eye	region	extraction	and	
grimace	pain	prediction,	we	propose	a	novel	structure	based	on	a	dilated	
convolutional	network.	The	experimental	results	are	promising,	showing	that	it	
is	possible	to	differentiate	among	the	pain	scale	of	the	mice

## Dataset

### Sub-dataset 1
<img src="https://github.com/AndreaVidal/WhiteFurredMice_Dataset/blob/main/Images/FaceDetection_example.png?raw" width="192" height="108">

- Annotation of bounding	boxes	around	the	mouse	 face. 
```
  "animalImage_1.png": [
        {
            "AnimalNumber": "1",
            "Boundingbox": {
                "x": "447",
                "y": "341",
                "w": "945",
                "h": "958"
            }
        }
    ],
```


### Sub-dataset 2
<img src="https://github.com/AndreaVidal/WhiteFurredMice_Dataset/blob/main/Images/EyeRegionDetection_example.png?raw" width="100" height="100">

- Grimace scale annotation and bounding	box	around	the eyes. 
```
 "animalImage_1.png": [
        {
            "AnimalNumber": "1",
            "GrimaceScale": "0",
            "Boundingbox": {
                "x": "233",
                "y": "370",
                "w": "502",
                "h": "476"
            }
        }
    ],
```

## Access to the data
```
import json

#Load data
json_file = open('file_name.json')
data = json.load(json_file)
json_file.close()

#Keys
keys_data = list(data.keys()) #Name of the image: image_name.png

#Access
data[keys_data[0]][0] #"0" is an example, it can be any number between 0 and len(keys_data)
data[keys_data[0]][0]['AnimalNumber']
data[keys_data[0]][0]['Boundingbox']['x']
data[keys_data[0]][0]['Boundingbox']['y']
data[keys_data[0]][0]['Boundingbox']['w']
data[keys_data[0]][0]['Boundingbox']['h']

```



## Reference
If you use this corpus, please cite the following paper:

Andrea Vidal, Sumit Jha, Shayne Hassler, Theodore Price, and Carlos Busso, "Face detection and grimace scale prediction of white furred mice," Machine Learning with Applications, vol. 8, pp. 100312, June 2022.

``` 
@article{Vidal_2022,
 	author={A. Vidal and S. Jha and S. Hassler and T. Price and C. Busso},
	title={Face detection and Grimace Scale Prediction of White Furred Mice},
	journal={Machine Learning with Applications},
	number={},
	volume={8},
	pages={100312},
	year={2022},
	month={June},
	doi={10.1016/j.mlwa.2022.100312},
}
```
