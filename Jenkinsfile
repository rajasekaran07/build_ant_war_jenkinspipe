node {
   // Mark the code checkout 'stage'....
   stage 'Checkout'
   
   git url: 'https://github.com/rajasekaran07/build_ant_war_jenkinspipe.git'

   // Get the ant tool.
   // ** NOTE: This 'ANT' ant tool must be configured
   // **       in the global configuration.           
   env.PATH = "${tool 'ant'}/bin:${env.PATH}"

   // Mark the code build 'stage'....
   stage 'Build'
   // Run the maven build
   sh 'ant'
   //fingerprint		
   stage 'Archive'
      step([$class: 'ArtifactArchiver', artifacts: '**/build/*.war', fingerprint: true])
}
