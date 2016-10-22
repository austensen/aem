``` r
library(tidyverse)
library(ggvis)

(rd <- read_csv("rd.csv", col_types = cols(Person = col_skip())))
```

    ## # A tibble: 30 × 3
    ##         x     z      y
    ##     <dbl> <int>  <dbl>
    ## 1  52.503     1 47.759
    ## 2  47.579     0 47.777
    ## 3  53.245     1 48.760
    ## 4  50.334     1 45.923
    ## 5  49.511     0 49.841
    ## 6  50.523     1 45.837
    ## 7  50.592     1 47.265
    ## 8  52.531     1 48.283
    ## 9  48.643     0 47.767
    ## 10 50.407     1 47.471
    ## # ... with 20 more rows

``` r
rd %>% 
  ggvis(~x, ~y) %>% 
  layer_points() %>% 
  group_by(z) %>% 
  layer_model_predictions(model = "lm", formula = y ~ x)
```

<!--html_preserve-->

<nav class="ggvis-control"> <a class="ggvis-dropdown-toggle" title="Controls" onclick="return false;"></a>
<ul class="ggvis-dropdown">
<li>
</li>
<li>
</li>
</ul>
</nav>

<script type="text/javascript">
  "data": [
    {
      "name": ".0",
      "format": {
        "type": "csv",
        "parse": {
          "x": "number",
          "y": "number"
        }
      },
      "values": "\"x\",\"y\"\n52.503,47.759\n47.579,47.777\n53.245,48.76\n50.334,45.923\n49.511,49.841\n50.523,45.837\n50.592,47.265\n52.531,48.283\n48.643,47.767\n50.407,47.471\n57.003,53.693\n47.04,45.692\n52.698,50.738\n48.707,47.597\n46.899,47.488\n46.85,47.854\n50.513,47.596\n49.425,48.437\n51.896,48.066\n48.75,49.063\n51.782,43.879\n49.871,50.121\n51.042,45.412\n46.586,46.824\n51.813,50.168\n45.45,45.882\n55.532,48.404\n48.445,49.359\n49.479,51.734\n51.296,45.317"
    },
    {
      "name": ".0/group_by1/model_prediction2_flat",
      "format": {
        "type": "csv",
        "parse": {
          "z": "number",
          "pred_": "number",
          "resp_": "number"
        }
      },
      "values": "\"z\",\"pred_\",\"resp_\"\n0,45.45,45.611398498236\n0,45.5059620253165,45.6672717676813\n0,45.5619240506329,45.7231450371267\n0,45.6178860759494,45.779018306572\n0,45.6738481012658,45.8348915760174\n0,45.7298101265823,45.8907648454628\n0,45.7857721518987,45.9466381149081\n0,45.8417341772152,46.0025113843535\n0,45.8976962025316,46.0583846537988\n0,45.9536582278481,46.1142579232442\n0,46.0096202531646,46.1701311926896\n0,46.065582278481,46.2260044621349\n0,46.1215443037975,46.2818777315803\n0,46.1775063291139,46.3377510010256\n0,46.2334683544304,46.393624270471\n0,46.2894303797468,46.4494975399164\n0,46.3453924050633,46.5053708093617\n0,46.4013544303797,46.5612440788071\n0,46.4573164556962,46.6171173482524\n0,46.5132784810127,46.6729906176978\n0,46.5692405063291,46.7288638871432\n0,46.6252025316456,46.7847371565885\n0,46.681164556962,46.8406104260339\n0,46.7371265822785,46.8964836954792\n0,46.7930886075949,46.9523569649246\n0,46.8490506329114,47.00823023437\n0,46.9050126582279,47.0641035038153\n0,46.9609746835443,47.1199767732607\n0,47.0169367088608,47.175850042706\n0,47.0728987341772,47.2317233121514\n0,47.1288607594937,47.2875965815968\n0,47.1848227848101,47.3434698510421\n0,47.2407848101266,47.3993431204875\n0,47.296746835443,47.4552163899328\n0,47.3527088607595,47.5110896593782\n0,47.408670886076,47.5669629288236\n0,47.4646329113924,47.6228361982689\n0,47.5205949367089,47.6787094677143\n0,47.5765569620253,47.7345827371596\n0,47.6325189873418,47.790456006605\n0,47.6884810126582,47.8463292760504\n0,47.7444430379747,47.9022025454957\n0,47.8004050632911,47.9580758149411\n0,47.8563670886076,48.0139490843864\n0,47.9123291139241,48.0698223538318\n0,47.9682911392405,48.1256956232772\n0,48.024253164557,48.1815688927225\n0,48.0802151898734,48.2374421621679\n0,48.1361772151899,48.2933154316132\n0,48.1921392405063,48.3491887010586\n0,48.2481012658228,48.405061970504\n0,48.3040632911392,48.4609352399493\n0,48.3600253164557,48.5168085093947\n0,48.4159873417722,48.57268177884\n0,48.4719493670886,48.6285550482854\n0,48.5279113924051,48.6844283177308\n0,48.5838734177215,48.7403015871761\n0,48.639835443038,48.7961748566215\n0,48.6957974683544,48.8520481260668\n0,48.7517594936709,48.9079213955122\n0,48.8077215189873,48.9637946649576\n0,48.8636835443038,49.0196679344029\n0,48.9196455696203,49.0755412038483\n0,48.9756075949367,49.1314144732936\n0,49.0315696202532,49.187287742739\n0,49.0875316455696,49.2431610121844\n0,49.1434936708861,49.2990342816297\n0,49.1994556962025,49.3549075510751\n0,49.255417721519,49.4107808205204\n0,49.3113797468354,49.4666540899658\n0,49.3673417721519,49.5225273594112\n0,49.4233037974684,49.5784006288565\n0,49.4792658227848,49.6342738983019\n0,49.5352278481013,49.6901471677472\n0,49.5911898734177,49.7460204371926\n0,49.6471518987342,49.801893706638\n0,49.7031139240506,49.8577669760833\n0,49.7590759493671,49.9136402455287\n0,49.8150379746835,49.969513514974\n0,49.871,50.0253867844194\n1,50.334,46.211176033058\n1,50.418417721519,46.2861484200254\n1,50.502835443038,46.3611208069928\n1,50.587253164557,46.4360931939601\n1,50.671670886076,46.5110655809275\n1,50.7560886075949,46.5860379678948\n1,50.8405063291139,46.6610103548622\n1,50.9249240506329,46.7359827418296\n1,51.0093417721519,46.8109551287969\n1,51.0937594936709,46.8859275157643\n1,51.1781772151899,46.9608999027316\n1,51.2625949367089,47.035872289699\n1,51.3470126582279,47.1108446766664\n1,51.4314303797468,47.1858170636337\n1,51.5158481012658,47.2607894506011\n1,51.6002658227848,47.3357618375684\n1,51.6846835443038,47.4107342245358\n1,51.7691012658228,47.4857066115031\n1,51.8535189873418,47.5606789984705\n1,51.9379367088608,47.6356513854379\n1,52.0223544303797,47.7106237724052\n1,52.1067721518987,47.7855961593726\n1,52.1911898734177,47.8605685463399\n1,52.2756075949367,47.9355409333073\n1,52.3600253164557,48.0105133202747\n1,52.4444430379747,48.085485707242\n1,52.5288607594937,48.1604580942094\n1,52.6132784810127,48.2354304811767\n1,52.6976962025316,48.3104028681441\n1,52.7821139240506,48.3853752551115\n1,52.8665316455696,48.4603476420788\n1,52.9509493670886,48.5353200290462\n1,53.0353670886076,48.6102924160135\n1,53.1197848101266,48.6852648029809\n1,53.2042025316456,48.7602371899482\n1,53.2886202531646,48.8352095769156\n1,53.3730379746835,48.910181963883\n1,53.4574556962025,48.9851543508503\n1,53.5418734177215,49.0601267378177\n1,53.6262911392405,49.135099124785\n1,53.7107088607595,49.2100715117524\n1,53.7951265822785,49.2850438987198\n1,53.8795443037975,49.3600162856871\n1,53.9639620253165,49.4349886726545\n1,54.0483797468354,49.5099610596218\n1,54.1327974683544,49.5849334465892\n1,54.2172151898734,49.6599058335566\n1,54.3016329113924,49.7348782205239\n1,54.3860506329114,49.8098506074913\n1,54.4704683544304,49.8848229944586\n1,54.5548860759494,49.959795381426\n1,54.6393037974684,50.0347677683934\n1,54.7237215189873,50.1097401553607\n1,54.8081392405063,50.1847125423281\n1,54.8925569620253,50.2596849292954\n1,54.9769746835443,50.3346573162628\n1,55.0613924050633,50.4096297032302\n1,55.1458101265823,50.4846020901975\n1,55.2302278481013,50.5595744771649\n1,55.3146455696203,50.6345468641322\n1,55.3990632911392,50.7095192510996\n1,55.4834810126582,50.7844916380669\n1,55.5678987341772,50.8594640250343\n1,55.6523164556962,50.9344364120017\n1,55.7367341772152,51.009408798969\n1,55.8211518987342,51.0843811859364\n1,55.9055696202532,51.1593535729037\n1,55.9899873417721,51.2343259598711\n1,56.0744050632911,51.3092983468385\n1,56.1588227848101,51.3842707338058\n1,56.2432405063291,51.4592431207732\n1,56.3276582278481,51.5342155077405\n1,56.4120759493671,51.6091878947079\n1,56.4964936708861,51.6841602816753\n1,56.5809113924051,51.7591326686426\n1,56.6653291139241,51.83410505561\n1,56.749746835443,51.9090774425773\n1,56.834164556962,51.9840498295447\n1,56.918582278481,52.059022216512\n1,57.003,52.1339946034794"
    },
    {
      "name": ".0/group_by1/model_prediction2",
      "source": ".0/group_by1/model_prediction2_flat",
      "transform": [
        {
          "type": "treefacet",
          "keys": [
            "data.z"
          ]
        }
      ]
    },
    {
      "name": "scale/x",
      "format": {
        "type": "csv",
        "parse": {
          "domain": "number"
        }
      },
      "values": "\"domain\"\n44.87235\n57.58065"
    },
    {
      "name": "scale/y",
      "format": {
        "type": "csv",
        "parse": {
          "domain": "number"
        }
      },
      "values": "\"domain\"\n43.3883\n54.1837"
    }
  ],
  "scales": [
    {
      "name": "x",
      "domain": {
        "data": "scale/x",
        "field": "data.domain"
      },
      "zero": false,
      "nice": false,
      "clamp": false,
      "range": "width"
    },
    {
      "name": "y",
      "domain": {
        "data": "scale/y",
        "field": "data.domain"
      },
      "zero": false,
      "nice": false,
      "clamp": false,
      "range": "height"
    }
  ],
  "marks": [
    {
      "type": "symbol",
      "properties": {
        "update": {
          "fill": {
            "value": "#000000"
          },
          "size": {
            "value": 50
          },
          "x": {
            "scale": "x",
            "field": "data.x"
          },
          "y": {
            "scale": "y",
            "field": "data.y"
          }
        },
        "ggvis": {
          "data": {
            "value": ".0"
          }
        }
      },
      "from": {
        "data": ".0"
      }
    },
    {
      "type": "group",
      "from": {
        "data": ".0/group_by1/model_prediction2"
      },
      "marks": [
        {
          "type": "line",
          "properties": {
            "update": {
              "stroke": {
                "value": "#000000"
              },
              "strokeWidth": {
                "value": 2
              },
              "x": {
                "scale": "x",
                "field": "data.pred_"
              },
              "y": {
                "scale": "y",
                "field": "data.resp_"
              },
              "fill": {
                "value": "transparent"
              }
            },
            "ggvis": {
              "data": {
                "value": ".0/group_by1/model_prediction2"
              }
            }
          }
        }
      ]
    }
  ],
  "legends": [],
  "axes": [
    {
      "type": "x",
      "scale": "x",
      "orient": "bottom",
      "layer": "back",
      "grid": true,
      "title": "x"
    },
    {
      "type": "y",
      "scale": "y",
      "orient": "left",
      "layer": "back",
      "grid": true,
      "title": "y"
    }
  ],
  "padding": null,
  "ggvis_opts": {
    "keep_aspect": false,
    "resizable": true,
    "padding": {},
    "duration": 250,
    "renderer": "svg",
    "hover_duration": 0,
    "width": 672,
    "height": 480
  },
  "handlers": null
};
</script>
<!--/html_preserve-->