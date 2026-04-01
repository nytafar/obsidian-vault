```yaml

          - type: vertical-stack
            cards:
              - type: custom:mini-graph-card
                name: 🌿 Bad
                icon: mdi:sprout
                entities:
                  - entity: sensor.soil_badsirkelblad_soil_moisture
                    color: "#4caf87"
                hours_to_show: 168
                points_per_hour: 0.5
                line_width: 2
                font_size: 75
                height: 60
                show:
                  fill: fade
                  extrema: true
                  icon: false
                  name: true
                  state: true
                  labels: false
                color_thresholds:
                  - value: 0
                    color: "#e05c5c"
                  - value: 25
                    color: "#e0a044"
                  - value: 50
                    color: "#4caf87"
              - type: custom:mini-graph-card
                name: 🌳 Ficus
                icon: mdi:tree
                entities:
                  - entity: sensor.soil_ficus_soil_moisture
                    color: "#66bb6a"
                hours_to_show: 168
                points_per_hour: 0.5
                line_width: 2
                font_size: 75
                height: 60
                show:
                  fill: fade
                  extrema: true
                  icon: false
                  name: true
                  state: true
                  labels: false
                color_thresholds:
                  - value: 0
                    color: "#e05c5c"
                  - value: 25
                    color: "#e0a044"
                  - value: 50
                    color: "#4caf87"
              - type: custom:mini-graph-card
                name: 🌸 Lilje m
                entities:
                  - entity: sensor.soil_fredslilje_m_soil_moisture
                    color: "#ab82d4"
                hours_to_show: 168
                points_per_hour: 0.5
                line_width: 2
                font_size: 75
                height: 60
                show:
                  fill: fade
                  extrema: true
                  icon: false
                  name: true
                  state: true
                  labels: false
                color_thresholds:
                  - value: 0
                    color: "#e05c5c"
                  - value: 25
                    color: "#e0a044"
                  - value: 50
                    color: "#ab82d4"
              - type: custom:mini-graph-card
                name: 🔥 Peispil
                entities:
                  - entity: sensor.soil_peispil_soil_moisture
                    color: "#ff8a65"
                hours_to_show: 168
                points_per_hour: 0.5
                line_width: 2
                font_size: 75
                height: 60
                show:
                  fill: fade
                  extrema: true
                  icon: false
                  name: true
                  state: true
                  labels: false
                color_thresholds:
                  - value: 0
                    color: "#e05c5c"
                  - value: 25
                    color: "#e0a044"
                  - value: 50
                    color: "#4caf87"
              - type: custom:mini-graph-card
                name: 🪴 WC
                entities:
                  - entity: sensor.soil_doklatrer_soil_moisture
                    color: "#29b6f6"
                hours_to_show: 168
                points_per_hour: 0.5
                line_width: 2
                font_size: 75
                height: 60
                show:
                  fill: fade
                  extrema: true
                  icon: false
                  name: true
                  state: true
                  labels: false
                color_thresholds:
                  - value: 0
                    color: "#e05c5c"
                  - value: 25
                    color: "#e0a044"
                  - value: 50
                    color: "#4caf87"
            grid_options:
              columns: 12
              rows: auto
              
```