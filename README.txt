START From FILE tabletennistraining.html


  '''
    for label in self.weights:
      for feature in self.features:
        self.weights[label][feature] = random.uniform(-1, 1)

    for iteration in range(self.max_iterations):
      print "Starting iteration ", iteration, "..."
      for i in range(len(trainingData)):
        output = []
        for label in self.weights:
          # for each perceptron p_l multiply w_l(f)*input(f) across all features f and store that in output[l]
          output.append(sum([self.weights[label][f] * trainingData[i][f] for f in self.features]))
        max_index = 0
        for j, x in enumerate(output):
          if x > output[max_index]:
            max_index = j
        if max_index != trainingLabels[i]:
          for feature in self.features:
            self.weights[max_index][feature] -= trainingData[i][feature]
            self.weights[trainingLabels[i]][feature] += trainingData[i][feature]



'''