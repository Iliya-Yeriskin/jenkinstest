pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'echo "Hello World"'
                sh '''
                    echo "Multiline shell steps works too"
                    ls -lah
                '''
                sh 'echo "Check delivery in-run allocation when menu items id 4 available on cells 'A' and 'B'
    ✓ Should get menu item 4 from cell 'A'
    ✓ Should get menu item 4 from cell 'A' and 'B'

  Check delivery in-run allocation when menu items id 4 finished at cell 'A'
    ✓ Should get menu item 4 from cell 'B'

  Check delivery in-run allocation when menu items id 4 available on cell 'A' and 'B'. Menu item id 5 available on cell 'C' and 'D'
    ✓ Should get menu item id 4 from cell 'A' and menu item id 5 from cell 'C'

  Check delivery in-run allocation when menu item id 4 available on cell 'A' and 'B'. Menu item id 5 available on cell 'D'
    ✓ Should get menu item id 4 from cell 'A' and menu item id 5 from cell 'D'

  Check delivery in-run allocation when menu item id 4 available on cell 'A' and 'B'. Two orders for the same item
    ✓ First order will taken from cell 'A', second order from cell 'B'

  Check delivery in-run allocation when menu item id 4 available on cell 'A' with 5 items in it. 5 orders for this item
    ✓ Each order should get a single item from cell 'A'

  Check delivery in-run allocation when menu item id 4 available on cells 'C' and 'D'
    ✓ First order should get items from 'C' and 'D', second order from 'D'

  Menu items id 6 does not exist on the container
itemsPlaceInContainer: {"4":[{"menuItemId":4,"cellIdentifier":"A","numberOfItemsStored":8},{"menuItemId":4,"cellIdentifier":"B","numberOfItemsStored":7}],"5":[{"menuItemId":5,"cellIdentifier":"C","numberOfItemsStored":8},{"menuItemId":5,"cellIdentifier":"D","numberOfItemsStored":8}]}
    ✓ Should throw an error


  9 passing (25ms)" >> build/test-reports/text.xml'
                sh 'pwd'
                sh 'ls -l build/test-reports/'
            }
        }
    }
    post {
        always {
           junit '/var/jenkins_home/workspace/test1_main/build/test-reports/test.xml'
        }    
    }
}
