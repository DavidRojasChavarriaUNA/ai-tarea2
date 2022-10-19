<!-- pages/books/[...slug].vue -->
<template>
  <div class="container">
    <HeaderView />
    <div class="row">
      <div class="three columns">
      </div>
      <div class="six columns">
        <h1>Planet: {{planet.planet}}</h1>
        <br>
        <table class="u-full-width">
          <thead>
            <tr>
              <th>Feature</th>
              <th>value</th>
            </tr>
          </thead>
          <tbody>
            <tr>
              <td>Planet</td>
              <td>{{planet.planet}}</td>
            </tr>
            <tr>
              <td>Color</td>
              <td>{{planet.color}}</td>
            </tr>
            <tr>
              <td>Mass (10^24kg)</td>
              <td>{{planet.mass}}</td>
            </tr>
            <tr>
              <td>Diameter (km)</td>
              <td>{{planet.diameter}}</td>
            </tr>
            <tr>
              <td>Density (kg/m^3)</td>
              <td>{{planet.density}}</td>
            </tr>
            <tr>
              <td>Surface Gravity(m/s^2)</td>
              <td>{{planet.surfaceGravity}}</td>
            </tr>
            <tr>
              <td>Escape Velocity (km/s)</td>
              <td>{{planet.escapeVelocity}}</td>
            </tr>
            <tr>
              <td>Rotation Period (hours)</td>
              <td>{{planet.rotationPeriod}}</td>
            </tr>
            <tr>
              <td>Length of Day (hours)</td>
              <td>{{planet.lengthOfDay}}</td>
            </tr>
            <tr>
              <td>Distance from Sun (10^6 km)</td>
              <td>{{planet.distanceFromSun}}</td>
            </tr> 
            <tr>
              <td>Perihelion (10^6 km)</td>
              <td>{{planet.perihelion}}</td>
            </tr>
            <tr>
              <td>Aphelion (10^6 km)</td>
              <td>{{planet.aphelion}}</td>
            </tr>
            <tr>
              <td>Orbital Period (days)</td>
              <td>{{planet.orbitalPeriod}}</td>
            </tr>
            <tr>
              <td>Orbital Velocity (km/s)</td>
              <td>{{planet.orbitalVelocity}}</td>
            </tr>
            <tr>
              <td>Orbital Inclination (degrees)</td>
              <td>{{planet.orbitalInclination}}</td>
            </tr>   
            <tr>
              <td>Orbital Eccentricity</td>
              <td>{{planet.orbitalEccentricity}}</td>
            </tr>
            <tr>
              <td>Obliquity to Orbit (degrees)</td>
              <td>{{planet.obliquityToOrbit}}</td>
            </tr>
            <tr>
              <td>Mean Temperature (C)</td>
              <td>{{planet.meanTemperature}}</td>
            </tr>
            <tr>
              <td>Surface Pressure (bars)</td>
              <td>{{planet.surfacePressure}}</td>
            </tr>
            <tr>
              <td>Number of Moons</td>
              <td>{{planet.numberOfMoons}}</td>
            </tr>
            <tr>
              <td>Ring System?</td>
              <td>{{planet.ringSystem}}</td>
            </tr>
            <tr>
              <td>Global Magnetic Field?</td>
              <td>{{planet.globalMagneticField}}</td>
            </tr>
          </tbody>
        </table>
      </div>
      <div class="two columns"></div>
    </div>
    <nuxt-link to="/">Atrás</nuxt-link>
    <FooterView />
  </div>
</template>
<script setup>
  const route = useRoute()
  const planets = await queryContent('planets').only('planetsList').findOne()
  const planet = planets.planetsList.find(planet => planet.num == route.params.slug)
</script>