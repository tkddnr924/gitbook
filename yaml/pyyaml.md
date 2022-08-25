# PyYaml

## Install

```
pip install PyYaml
```

## Example

{% embed url="https://github.com/tkddnr924/yaml_parser_test" %}

## How to use

### Read Yaml

```
import yaml

def read_yaml(path, all=True):
    try:
        with open(path, 'r') as f:
            contents = yaml.load_all(f, yaml.FullLoader) if all \
                else yaml.load(f, yaml.FullLoader)
            return list(contents) if all else [contents]
    except Exception as e:
        print e
        sys.exit(1)
```

### Write Yaml

```
import yaml

def write_yaml(path, data, mode='a'):
    try:
        with open(path, mode) as f:
            yaml.dump(data, f, explicit_start=True)
    except Exception as e:
        print e
        sys.exit(1)
```

