package main

import (
	"fmt"
	"github.com/spf13/cobra"
	"os"
)

func main() {
	var name string

	rootCmd := &cobra.Command{
		Use:   "mycli",
		Short: "My awesome CLI",
	}

	greetCmd := &cobra.Command{
		Use:   "greet",
		Short: "Greet the user",
		Run: func(cmd *cobra.Command, args []string) {
			fmt.Printf("Hello, %s!\n", name)
		},
	}

	greetCmd.Flags().StringVarP(&name, "name", "n", "", "Name of the user")
	greetCmd.MarkFlagRequired("name")

	rootCmd.AddCommand(greetCmd)

	if err := rootCmd.Execute(); err != nil {
		fmt.Println(err)
		os.Exit(1)
	}
}
