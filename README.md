# -help-python
from flask import Flask
import json
app = Flask(__name__)



@app.route("/")
def root():
    return print_restruants(inputData)


def only_important(restaurant):
  tags = restaurant["tags"]
  if "cuisine" in tags.keys():
    return {
    "name": tags["name"],
    "cuisine": tags["cuisine"] 
  }
  else:
    return "Not valid"

  


    


def print_restruants(variable):
  result = []
  for restaurant in variable:
    result.append(only_important(restaurant))
  return json.dumps(result)
  # return variable["tags"]["cuisine"]

if __name__ == "__main__":
    app.run(debug=True)
